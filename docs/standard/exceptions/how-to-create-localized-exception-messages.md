---
title: "Procedura: creare eccezioni definite dall'utente con messaggi di eccezione localizzati"
description: Informazioni su come creare eccezioni definite dall'utente con messaggi di eccezione localizzati
author: Youssef1313
ms.author: ronpet
ms.date: 09/13/2019
ms.openlocfilehash: 1e5ef5658e4cb71d0689a1786494eaec57d4e7fb
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332991"
---
# <a name="how-to-create-user-defined-exceptions-with-localized-exception-messages"></a>Procedura: creare eccezioni definite dall'utente con messaggi di eccezione localizzati

In questo articolo si apprenderà come creare eccezioni definite dall'utente ereditate dalla classe di base <xref:System.Exception> con messaggi di eccezione localizzati tramite assembly satellite.

## <a name="create-custom-exceptions"></a>Creare eccezioni personalizzate

.NET contiene molte eccezioni diverse che è possibile usare. Tuttavia, in alcuni casi in cui nessuno soddisfa le proprie esigenze, è possibile creare eccezioni personalizzate.

Si supponga di voler creare un `StudentNotFoundException` che contiene una proprietà `StudentName`.
Per creare un'eccezione personalizzata, attenersi alla procedura seguente:

1. Creare una classe serializzabile che erediti da <xref:System.Exception>. Il nome della classe deve terminare con "Exception":

    ```csharp
    [Serializable]
    public class StudentNotFoundException : Exception { }
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

## <a name="create-localized-exception-messages"></a>Creare messaggi di eccezione localizzati

È stata creata un'eccezione personalizzata, che può essere generata ovunque con codice simile al seguente:

```csharp
throw new StudentNotFoundException("The student cannot be found.", "John");
```

Il problema con la riga precedente è che "lo studente non è stato trovato". è solo una stringa costante. In un'applicazione localizzata è necessario avere messaggi diversi a seconda delle impostazioni cultura dell'utente.
Gli [assembly satellite](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md) sono un modo efficace per eseguire questa operazione. Un assembly satellite è un file con estensione dll che contiene risorse per una lingua specifica. Quando si richiede una specifica risorsa in fase di esecuzione, CLR trova tale risorsa a seconda delle impostazioni cultura dell'utente. Se non viene trovato alcun assembly satellite per tali impostazioni cultura, vengono utilizzate le risorse delle impostazioni cultura predefinite.

Per creare i messaggi di eccezione localizzati:

1. Creare una nuova cartella denominata *Resources* per conservare i file di risorse.
1. Aggiungere un nuovo file di risorse. Per eseguire questa operazione in Visual Studio, fare clic con il pulsante destro del mouse sulla cartella in **Esplora soluzioni**e selezionare **Aggiungi** -> **nuovo elemento** -> **file di risorse**. Denominare il file *ExceptionMessages. resx*. Questo è il file di risorse predefinito.
1. Aggiungere una coppia nome/valore per il messaggio di eccezione, come illustrato nella figura seguente: @no__t 0Add le risorse alle impostazioni cultura predefinite @ no__t-1
1. Aggiungere un nuovo file di risorse per il francese. Denominarlo *ExceptionMessages.fr-fr. resx*.
1. Aggiungere nuovamente una coppia nome/valore per il messaggio di eccezione, ma con un valore francese: @no__t 0Add le risorse per le impostazioni cultura fr-FR @ no__t-1
1. Dopo aver compilato il progetto, la cartella di output di compilazione deve contenere la cartella *fr-fr* con un file con estensione *dll* , ovvero l'assembly satellite.
1. L'eccezione viene generata con codice simile al seguente:

    ```csharp
    var resourceManager = new ResourceManager("FULLY_QIALIFIED_NAME_OF_RESOURCE_FILE", Assembly.GetExecutingAssembly());
    throw new StudentNotFoundException(resourceManager.GetString("StudentNotFound"), "John");
    ```

  > [!NOTE]
  > Se il nome del progetto è `TestProject` e il file di risorse *ExceptionMessages. resx* risiede nella cartella *Resources* del progetto, il nome completo del file di risorse è `TestProject.Resources.ExceptionMessages`.

## <a name="see-also"></a>Vedere anche

- [Come creare eccezioni definite dall'utente](how-to-create-user-defined-exceptions.md)
- [Creazione di assembly satellite per le applicazioni desktop](../../framework/resources/creating-satellite-assemblies-for-desktop-apps.md)
- [base (C# riferimento)](../../csharp/language-reference/keywords/base.md)
- [Questo (C# riferimento)](../../csharp/language-reference/keywords/this.md)
