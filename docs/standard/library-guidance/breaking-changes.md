---
title: Modifiche di rilievo e librerie .NET
description: Procedure consigliate per esplorare le modifiche di rilievo durante la creazione di librerie .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 2cbd9e0a818b52aede6c9b1f60fdf52dcbd7b96f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79400421"
---
# <a name="breaking-changes"></a>Modifiche di rilievo

Per una libreria .NET è importante trovare un equilibrio tra la stabilità per gli utenti esistenti e l'innovazione per il futuro. Gli autori di libreria effettuano il refactoring e rielaborano il codice finché non è perfetto. Interrompere gli utenti esistenti ha tuttavia un impatto negativo, soprattutto per le librerie di basso livello.

## <a name="project-types-and-breaking-changes"></a>Tipi di progetto e modifiche di rilievo

A seconda di come una libreria viene usata dalla community .NET, cambia l'effetto delle modifiche di rilievo sullo sviluppo per utenti finali.

- Le **librerie di basso e medio livello**, ad esempio un serializzatore, il parser HTML, un Object-Relational Mapper (ORM) di database o un framework Web, sono gli elementi che più risentono delle modifiche di rilievo.

  I pacchetti di blocchi predefiniti sono usati dagli sviluppatori per utenti finali per compilare le applicazioni, e da altre librerie come dipendenze NuGet. Ad esempio, un'applicazione viene compilata usando un client open source per chiamare un servizio Web. Un aggiornamento di rilievo a una dipendenza usata dal client non è un'operazione possibile. È il client open source che deve essere modificato, sul quale non si ha controllo. È necessario trovare versioni compatibili di librerie o inviare una correzione alla libreria client e attendere una nuova versione. Il caso peggiore è quando si vogliono usare due librerie che dipendono reciprocamente da versioni incompatibili di una terza libreria.

- Le **librerie di alto livello**, ad esempio una suite di controlli dell'interfaccia utente, sono meno sensibili alle modifiche di rilievo.

  Le librerie di alto livello hanno un riferimento diretto all'interno di un'applicazione per utenti finali. In caso di modifiche di rilievo, lo sviluppatore può scegliere di eseguire l'aggiornamento alla versione più recente oppure può modificare l'applicazione per accettare le modifiche di rilievo.

✔️ CONSIDERARE quale sarà l'uso della libreria. Valutare l'effetto che le modifiche di rilievo avranno sulle applicazioni e sulle librerie in cui è usata la libreria.

✔️ RIDURRE AL MINIMO le modifiche di rilievo quando si sviluppa una libreria .NET di basso livello.

✔️CONSIDERARE  la possibilità di pubblicare una riscrittura principale di una libreria come nuovo pacchetto NuGet.

## <a name="types-of-breaking-changes"></a>Tipi di modifiche di rilievo

Le modifiche di rilievo vengono classificate in categorie diverse e non hanno tutte lo stesso impatto.

### <a name="source-breaking-change"></a>Modifica dell'origine

Una modifica dell'origine non ha effetto sull'esecuzione del programma, ma genererà errori di compilazione quando l'applicazione sarà ricompilata. Ad esempio, un nuovo overload può creare ambiguità nelle chiamate al metodo che non erano precedentemente ambigue, oppure un parametro rinominato interromperà i chiamanti che usano parametri denominati.

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

Poiché la modifica dell'origine è dannosa solo quando gli sviluppatori ricompilano le applicazioni, è il tipo di modifica che comporta meno problemi. Gli sviluppatori possono risolvere facilmente il codice di origine interrotto.

### <a name="behavior-breaking-change"></a>Modifica del comportamento

Le modifiche del comportamento sono i tipi di modifica più comuni. Quasi tutte le modifiche del comportamento possono creare un'interruzione. Le modifiche alla libreria, ad esempio firme del metodo, eccezioni generate o formati di dati di input o output, possono avere tutte un effetto negativo sui consumer della libreria. Perfino la correzione di un bug può essere considerata una modifica di rilievo se gli utenti si basavano sul comportamento precedentemente interrotto.

È una buona soluzione aggiungere funzionalità e migliorare i comportamenti non corretti. Tuttavia è consigliabile fare molta attenzione, poiché gli utenti esistenti potrebbero riscontrare difficoltà a eseguire l'upgrade. Per aiutare gli sviluppatori a gestire le modifiche del comportamento, è consigliabile nascondere tali modifiche nelle impostazioni. Le impostazioni consentono agli sviluppatori di eseguire l'aggiornamento alla versione più recente della libreria e al tempo stesso scegliere se accettare o rifiutare esplicitamente le modifiche di rilievo. Questa strategia consente agli sviluppatori di rimanere aggiornati, consentendo al codice usato di adattarsi nel tempo.

Ad esempio, ASP.NET Core MVC include il concetto di una [versione di compatibilità](/aspnet/core/mvc/compatibility-version) che consente di modificare la funzionalità abilitate e disabilitate in `MvcOptions`.

✔️ CONSIDERARE di lasciare disabilitate le nuove funzionalità per impostazione predefinita qualora abbiano effetto sugli utenti esistenti, e consentire agli sviluppatori di accettare esplicitamente la funzionalità con un'impostazione.

### <a name="binary-breaking-change"></a>Modifica di tipo binario

Una modifica di tipo binario si verifica quando viene modificata l'API pubblica della libreria. In questo caso gli assembly compilati sulla base delle versioni precedenti della libreria non possono più chiamare l'API. Ad esempio, se si modifica la firma del metodo aggiungendo una nuovo parametro, gli assembly compilati sulla base delle versioni precedenti della libreria genereranno un'eccezione di tipo <xref:System.MissingMethodException>.

Una modifica di tipo binario può interrompere anche un **intero assembly**. La rinomina di un assembly con `AssemblyName` modificherà l'identità dell'assembly, esattamente come succede se si aggiunge, rimuove o modifica la chiave per la creazione di nomi sicuri. La modifica di un'identità dell'assembly interrompe l'intero codice compilato in cui viene usata.

❌NON modificare il nome di un assembly.

❌NON aggiungere, rimuovere o modificare la chiave di denominazione sicura.

✔️ CONSIDERARE l'uso di classi di base astratte al posto di interfacce.

> Se si aggiunge un qualsiasi elemento a un'interfaccia, i tipi esistenti che la implementano non saranno eseguiti correttamente. Una classe di base astratta consente di aggiungere un'impostazione virtuale.

✔️ CONSIDERARE di posizionare la classe <xref:System.ObsoleteAttribute> su tipi e membri che non saranno rimossi. L'attributo deve avere istruzioni per l'aggiornamento del codice affinché non sia più usata l'API obsoleta.

> Il codice che chiama i tipi e i metodi con la classe <xref:System.ObsoleteAttribute> genererà un avviso di compilazione con il messaggio specificato per l'attributo. Gli avvisi consentono a chi usa la superficie dell'API obsoleta di avere il tempo necessario per eseguire la migrazione. In questo modo, al momento della rimozione dell'API obsoleta, non sarà più usata da molti.

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

✔️ CONSIDERARE di mantenere tipi e metodi con la classe <xref:System.ObsoleteAttribute> in modo illimitato nelle librerie di livello medio e basso.

> La rimozione delle API è considerata una modifica di tipo binario. Valutare di mantenere tipi e metodi obsoleti se i costi di manutenzione sono bassi e non si richiedono interventi tecnici importanti alla libreria. Se i tipi e i metodi non vengono rimossi, si evita di assistere agli scenari peggiori descritti in precedenza.

## <a name="see-also"></a>Vedere anche

- [Considerazioni su versione e aggiornamento per gli sviluppatori C#](../../csharp/whats-new/version-update-considerations.md)
- [A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net) (Ottima guida alle modifiche di rilievo delle API in .NET)
- [Regole di modifica di rilievo .NET](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[Indietro](versioning.md)
