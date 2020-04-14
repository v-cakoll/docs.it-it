---
title: Come creare eccezioni definite dall'utente con messaggi di eccezione localizzatiHow to create user-defined exceptions with localized exception messages
description: Informazioni su come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
author: Youssef1313
dev_langs:
- csharp
- vb
ms.date: 09/13/2019
ms.openlocfilehash: fa0bbfdbfc9408302eec2edd4e4ee4503d2612c7
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243349"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Come creare eccezioni definite dall'utente con messaggi di eccezione localizzatiHow to create user-defined exceptions with localized exception messages

In questo articolo verrà illustrato come creare eccezioni definite dall'utente <xref:System.Exception> ereditate dalla classe base con messaggi di eccezione localizzati tramite assembly satellite.

## <a name="create-custom-exceptions"></a>Creare eccezioni personalizzate

.NET contiene molte eccezioni diverse che è possibile utilizzare. Tuttavia, in alcuni casi quando nessuno di essi soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.

Si supponga di voler creare `StudentNotFoundException` un `StudentName` che contiene una proprietà.
Per creare un'eccezione personalizzata, attenersi alla seguente procedura:

1. Creare una classe serializzabile che <xref:System.Exception>eredita da . Il nome della classe deve terminare con "Exception":

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception
    End Class
    ```

1. Aggiungere i costruttori predefiniti:Add the default constructors:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub
    End Class
    ```

1. Definire eventuali proprietà e costruttori aggiuntivi:Define any additional properties and constructors:

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception
    {
        public string StudentName { get; }

        public StudentNotFoundException() { }

        public StudentNotFoundException(string message)
            : base(message) { }

        public StudentNotFoundException(string message, Exception inner)
            : base(message, inner) { }

        public StudentNotFoundException(string message, string studentName)
            : this(message)
        {
            StudentName = studentName;
        }
    }
    ```

    ```vb
    <Serializable>
    Public Class StudentNotFoundException
        Inherits Exception

        Public ReadOnly Property StudentName As String

        Public Sub New()
        End Sub

        Public Sub New(message As String)
            MyBase.New(message)
        End Sub

        Public Sub New(message As String, inner As Exception)
            MyBase.New(message, inner)
        End Sub

        Public Sub New(message As String, studentName As String)
            Me.New(message)
            StudentName = studentName
        End Sub
    End Class
    ```

## <a name="create-localized-exception-messages"></a>Creare messaggi di eccezione localizzatiCreate localized exception messages

È stata creata un'eccezione personalizzata ed è possibile generarla ovunque con codice simile al seguente:You have created a custom exception, and you can throw it anywhere with code like the following:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

Il problema con la `"The student cannot be found."` riga precedente è che è solo una stringa costante. In un'applicazione localizzata, si desidera avere messaggi diversi a seconda delle impostazioni cultura dell'utente.
[Gli assembly satellitari](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un buon modo per farlo. Un assembly satellite è una DLL che contiene risorse per una lingua specifica. Quando si richiede una risorsa specifica in fase di esecuzione, CLR trova tale risorsa in base alle impostazioni cultura dell'utente. Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.

Per creare i messaggi di eccezione localizzati:

1. Creare una nuova cartella denominata *Resources* per contenere i file di risorse.
1. Aggiungere un nuovo file di risorse. A tale scopo in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e scegliere **Aggiungi** > **nuovo file** > **di risorse**elemento . Assegnare al file il nome *ExceptionMessages.resx*. Questo è il file di risorse predefinito.
1. Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nell'immagine seguente:Add a name/value pair for your exception message, like the following image shows:

   ![Aggiungere risorse alle impostazioni cultura predefiniteAdd resources to the default culture](media/add-resources-to-default-culture.jpg)

1. Aggiungere un nuovo file di risorse per il francese. Denominarlo *ExceptionMessages.fr-FR.resx*.
1. Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese:Add a name/value pair for the exception message again, but with a French value:

   ![Aggiungere risorse alle impostazioni cultura fr-FR](media/add-resources-to-fr-culture.jpg)

1. Dopo aver compilato il progetto, la cartella dell'output di compilazione deve contenere la cartella *fr-FR* con un file *DLL,* ovvero l'assembly satellite.
1. Generare l'eccezione con codice simile al seguente:

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    ```vb
    Dim resourceManager As New ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly())
    Throw New StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John")
    ```

    > [!NOTE]
    > Se il nome `TestProject` del progetto è e il file di risorse *ExceptionMessages.resx* si trova nella `TestProject.Resources.ExceptionMessages`cartella *Resources* del progetto, il nome completo del file di risorse è .

## <a name="see-also"></a>Vedere anche

- [Come creare eccezioni definite dall'utenteHow to create user-defined exceptions](how-to-create-user-defined-exceptions.md)
- [Creazione di assembly satellite per applicazioni desktop](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (Riferimenti per C#)](../../csharp/language-reference/keywords/base.md)
- [this (Riferimenti per C#)](../../csharp/language-reference/keywords/this.md)
