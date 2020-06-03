---
title: Come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
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
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Come creare eccezioni definite dall'utente con messaggi di eccezione localizzati

In questo articolo si apprenderà come creare eccezioni definite dall'utente ereditate dalla <xref:System.Exception> classe base con messaggi di eccezione localizzati tramite assembly satellite.

## <a name="create-custom-exceptions"></a>Creare eccezioni personalizzate

.NET contiene molte eccezioni diverse che è possibile usare. Tuttavia, in alcuni casi in cui nessuno soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.

Si supponga di voler creare un oggetto `StudentNotFoundException` che contiene una `StudentName` Proprietà.
Per creare un'eccezione personalizzata, attenersi alla procedura seguente:

1. Creare una classe serializzabile che eredita da <xref:System.Exception> . Il nome della classe deve terminare con "Exception":

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

1. Aggiungere i costruttori predefiniti:

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

1. Definire le proprietà e i costruttori aggiuntivi:

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

## <a name="create-localized-exception-messages"></a>Creare messaggi di eccezione localizzati

È stata creata un'eccezione personalizzata, che può essere generata ovunque con codice simile al seguente:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

```vb
Throw New StudentNotFoundException("The student cannot be found.", "John")
```

Il problema con la riga precedente è `"The student cannot be found."` semplicemente una stringa costante. In un'applicazione localizzata è necessario avere messaggi diversi a seconda delle impostazioni cultura dell'utente.
Gli [assembly satellite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un modo efficace per eseguire questa operazione. Un assembly satellite è un file con estensione dll che contiene risorse per una lingua specifica. Quando si richiede una specifica risorsa in fase di esecuzione, CLR trova tale risorsa a seconda delle impostazioni cultura dell'utente. Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.

Per creare i messaggi di eccezione localizzati:

1. Creare una nuova cartella denominata *Resources* per conservare i file di risorse.
1. Aggiungere un nuovo file di risorse. Per eseguire questa operazione in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e scegliere **Aggiungi**  >  **nuovo elemento**  >  **risorse file**. Denominare il file *ExceptionMessages. resx*. Questo è il file di risorse predefinito.
1. Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nella figura seguente:

   ![Aggiungere risorse alle impostazioni cultura predefinite](media/add-resources-to-default-culture.jpg)

1. Aggiungere un nuovo file di risorse per il francese. Denominarlo *ExceptionMessages.fr-fr. resx*.
1. Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese:

   ![Aggiungere risorse alle impostazioni cultura fr-FR](media/add-resources-to-fr-culture.jpg)

1. Dopo aver compilato il progetto, la cartella di output di compilazione deve contenere la cartella *fr-fr* con un file con estensione *dll* , ovvero l'assembly satellite.
1. L'eccezione viene generata con codice simile al seguente:

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

    ```vb
    Dim resourceManager As New ResourceManager("FULLY_QUALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly())
    Throw New StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John")
    ```

    > [!NOTE]
    > Se il nome del progetto è `TestProject` e il file di risorse *ExceptionMessages. resx* risiede nella cartella *Resources* del progetto, il nome completo del file di risorse è `TestProject.Resources.ExceptionMessages` .

## <a name="see-also"></a>Vedere anche

- [Come creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md)
- [Creazione di assembly satellite per applicazioni desktop](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (Riferimenti per C#)](../../csharp/language-reference/keywords/base.md)
- [this (Riferimenti per C#)](../../csharp/language-reference/keywords/this.md)
