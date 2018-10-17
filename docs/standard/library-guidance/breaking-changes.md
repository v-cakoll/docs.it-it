---
title: Modifiche di rilievo apportate e librerie .NET
description: Le procedure consigliate per lo spostamento delle modifiche di rilievo durante la creazione di librerie .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370062"
---
# <a name="breaking-changes"></a>Modifiche di rilievo

È importante per una libreria .NET trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro. Gli autori di libreria fare affidamento a refactoring e rethinking codice fino a quando non è perfetto, ma gli utenti esistenti di rilievo ha un impatto negativo, in particolare per le librerie di basso livello.

## <a name="project-types-and-breaking-changes"></a>Tipi di progetto e le modifiche di rilievo

Utilizzo di una libreria dalla community .NET cambia l'effetto delle modifiche di rilievo per sviluppatori di dati gestito dall'utente.

* **Basso e medio livello librerie** come un serializzatore, il parser HTML, mapper relazionale a oggetti di database o framework web sono i più interessati da modifiche di rilievo.

  Blocchi predefiniti vengono utilizzati dagli sviluppatori per l'utente finale per compilare applicazioni e da altre librerie come dipendenze di NuGet. Ad esempio, si sta creando un'applicazione e si usa un client open source per chiamare un servizio web. Un aggiornamento di rilievo a una dipendenza che usa il client non che è possibile risolvere. Questo è il client open source che deve essere modificato e si ha alcun controllo su di esso. È necessario trovare versioni compatibili di librerie o inviare una correzione per la libreria client e attendere una nuova versione. La situazione peggiore è se si desidera utilizzare due librerie che dipendono dalle versioni incompatibili di una libreria di terza.

* **Librerie di alto livello** come una suite di interfaccia utente sono meno sensibili alle modifiche di rilievo controlli.

  Librerie di alto livello vengono fatto riferimento diretto in un'applicazione dell'utente finale. Se si verificano modifiche di rilievo, lo sviluppatore può scegliere di aggiornare la versione più recente oppure può modificare l'applicazione per lavorare con le modifiche di rilievo.

**Eseguire operazioni ✔️** considerare come verrà usata la libreria. Quale effetto avrà le modifiche di rilievo su applicazioni e librerie che usano?

**Eseguire operazioni ✔️** ridurre al minimo le modifiche di rilievo quando si sviluppa una libreria .NET di basso livello.

**Provare a ✔️** pubblicazione principale riscrittura di una raccolta come un nuovo pacchetto NuGet.

## <a name="types-of-breaking-changes"></a>Tipi di modifiche di rilievo

Modifiche di rilievo apportate possono essere suddivise in categorie diverse e non sono altrettanto con impatto elevati.

### <a name="source-breaking-change"></a>Modifica di rilievo di origine

Un'origine di modifica di rilievo non influisce sull'esecuzione del programma ma causerà errori di compilazione la volta successiva che l'applicazione viene ricompilata. Ad esempio, un nuovo overload può creare ambiguità nelle chiamate al metodo che erano in precedenza non ambigue, o un parametro rinominato interromperà i chiamanti che utilizzano parametri denominati.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Poiché un'origine di modifica di rilievo è dannosa solo quando gli sviluppatori di compilare nuovamente le proprie applicazioni, è meno dirompenti modifica di rilievo. Gli sviluppatori possono risolvere facilmente il proprio codice di origine interrotto.

### <a name="behavior-breaking-change"></a>Modifica di rilievo di comportamento

Modifiche del comportamento sono il tipo più comune di modifica di rilievo: quasi qualsiasi modifica nel comportamento è stato possibile interrompere un utente. Modifiche alla raccolta, ad esempio le firme di metodo, le eccezioni generate o di input o output formati di dati, tutto da influire negativamente sui consumer della libreria. Anche una correzione di bug può qualificare modifiche a posteriori se gli utenti si basavano sui comportamenti interrotti in precedenza.

Aggiunta di funzionalità e comportamenti non corretti di miglioramento è positivo, ma senza care può risultare molto difficile per gli utenti esistenti eseguire l'aggiornamento. Uno degli approcci per aiutare gli sviluppatori di affrontare comportamento modifiche di rilievo è per nasconderle dietro le impostazioni. Le impostazioni consentono agli sviluppatori di aggiornare la versione più recente della libreria allo stesso tempo scelta acconsentire o rifiutare le modifiche di rilievo. Questa strategia consente agli sviluppatori di rimanere aggiornati, consentendo al contempo il proprio codice dispendiosa in termini di adattare nel corso del tempo.

Ad esempio, ASP.NET Core MVC include il concetto di una [versione di compatibilità](/aspnet/core/mvc/compatibility-version) che consente di modificare la funzionalità abilitata e disabilitata in `MvcOptions`.

**Provare a ✔️** lasciando le nuove funzionalità per impostazione predefinita, se interessa gli utenti esistenti e consentono agli sviluppatori di acconsentire esplicitamente alla funzionalità con un'impostazione.

### <a name="binary-breaking-change"></a>Modifica di rilievo binario

Un file binario modifica di rilievo accade quando si modifica l'API pubblica della libreria, in modo che gli assembly compilati con le versioni precedenti della libreria non sono più in grado di chiamare l'API. Ad esempio, la modifica di firma del metodo aggiungendo un nuovo parametro causa gli assembly compilati con la versione meno recente della libreria generare un <xref:System.MissingMethodException>.

Un file binario modifica di rilievo consentono inoltre di suddividere un' **intero assembly**. Ridenominazione di un assembly con `AssemblyName` modificheranno l'identità dell'assembly, verrà aggiunta, rimozione o Modifica chiave denominazione sicuro dell'assembly. Una modifica di identità di un assembly può compromettere tutto il codice compilato che lo utilizza.

**NON ❌** cambiare un nome di assembly.

**NON ❌** aggiungere, rimuovere o modificare la chiave di denominazione intenso.

**Provare a ✔️** usando le classi base astratte anziché le interfacce.

> Aggiunta di qualsiasi elemento a un'interfaccia causerà esistenti i tipi che implementano l'esito negativo. Una classe base astratta consente di aggiungere un'implementazione virtuale predefinito.

**✔️ si consiglia** posizionare il <xref:System.ObsoleteAttribute> su tipi e membri che si intendono rimuovere. L'attributo deve avere le istruzioni per l'aggiornamento del codice non è più usare l'API obsoleta.

> Il codice che chiama i tipi e metodi con il <xref:System.ObsoleteAttribute> genererà un avviso di compilazione con il messaggio fornito all'attributo. Gli avvisi consentono di chi utilizza il tempo di superficie API obsoleto per eseguire la migrazione in modo che quando viene rimossa l'API obsoleta, la maggior parte non sono più usarlo.

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

## <a name="see-also"></a>Vedere anche

* [Considerazioni sulla versione e aggiornamento per gli sviluppatori c#](../../csharp/whats-new/version-update-considerations.md)
* [Una Guida definitiva per API-ultime modifiche in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [Regole di modifica di rilievo CoreFX](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[Precedente](./versioning.md)
