---
title: Creazione di pacchetti e distribuzione delle risorse nelle app .NET
description: Creare un pacchetto e distribuire le risorse nelle app .NET usando un assembly principale (hub) e gli assembly satellite (spoke). Un spoke contiene risorse localizzate ma senza codice.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deploying applications [.NET Framework], resources
- resource files, deploying
- hub-and-spoke resource deployment model
- resource files, packaging
- application resources, packaging
- single resource assembly
- satellite assemblies
- default culture for applications
- names [.NET Framework], resources
- fallback process for resources
- grouping cultures
- application resources, deploying
- application resources, naming conventions
- culture, packaging and deploying resources
- resource files, naming conventions
- packaging application resources
- application resources, fallback processes
- resource files, fallback processes
- localizing resources
- neutral cultures
ms.assetid: b224d7c0-35f8-4e82-a705-dd76795e8d16
ms.openlocfilehash: 7b06ca4444b75f0a7002323b32732dd4f855f692
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166189"
---
# <a name="packaging-and-deploying-resources-in-net-apps"></a>Creazione di pacchetti e distribuzione delle risorse nelle app .NET

Per recuperare le risorse localizzate le applicazioni usano .NET Framework Resource Manager, rappresentato dalla classe <xref:System.Resources.ResourceManager>. Resource Manager presuppone l'uso di un modello hub e spoke per la creazione di pacchetti e la distribuzione delle risorse. L'hub è l'assembly principale che contiene il codice eseguibile non localizzabile e le risorse di un singolo set di impostazioni cultura, denominate impostazioni cultura neutre o predefinite. Le impostazioni cultura predefinite sono le impostazioni di fallback per l'applicazione, ovvero le impostazioni che vengono usate quando non si trovano le risorse localizzate. Ogni spoke si connette a un assembly satellite contenente le risorse di determinate impostazioni cultura, ma non contiene alcun codice.

Questo modello presenta diversi vantaggi:

- È possibile aggiungere in modo incrementale risorse per nuove impostazioni cultura dopo la distribuzione di un'applicazione. Lo sviluppo di risorse specifiche per le impostazioni cultura può richiedere molto tempo. Questo modello consente di rilasciare l'applicazione principale e quindi di distribuire in un secondo momento le risorse specifiche delle impostazioni cultura.
- È possibile aggiornare e modificare gli assembly satellite di un'applicazione senza ricompilare l'applicazione.
- L'applicazione potrà caricare solo gli assembly satellite che contengono le risorse necessarie per impostazioni cultura specifiche. In questo modo è possibile ridurre notevolmente l'uso delle risorse di sistema.

 Tuttavia il modello presenta anche alcuni svantaggi:

- È necessario gestire più set di risorse.
- Il costo iniziale del test un'applicazione è più elevato, perché è necessario sottoporre a test diverse configurazioni. Si noti che a lungo termine sarà più semplice ed economico testare un'applicazione centrale con vari satelliti che testare e gestire più versioni internazionali parallele.

## <a name="resource-naming-conventions"></a>Convenzioni di denominazione delle risorse

Quando si includono nel pacchetto le risorse dell'applicazione è necessario denominarle in base alle convenzioni previste dal Common Language Runtime. Il runtime identifica una risorsa in base al nome delle impostazioni cultura. A ogni set di impostazioni cultura viene assegnato un nome univoco, in genere una combinazione di un nome impostazioni cultura di due lettere minuscole associato a una lingua e (se necessario) un nome impostazioni cultura secondarie di due lettere maiuscole associato a un paese o a una regione. Il nome delle impostazioni cultura secondarie segue il nome delle impostazioni cultura ed è separato da un trattino (-). Ad esempio ja-JP corrisponde al giapponese parlato in Giappone, en-US corrisponde all'inglese parlato negli Stati Uniti d'America, de-DE corrisponde al tedesco parlato in Germania, de-AT corrisponde al tedesco parlato in Austria. Vedere la colonna **Language tag** (Tag di lingua) nell'[elenco di nomi di lingua/area geografica supportati da Windows](https://docs.microsoft.com/openspecs/windows_protocols/ms-lcid/a9eac961-e77d-41a6-90a5-ce1a8b0cdb9c). I nomi delle impostazioni cultura seguono lo standard definito da [BCP 47](https://tools.ietf.org/html/bcp47).

> [!NOTE]
> Esistono alcune eccezioni per i nomi delle impostazioni cultura di due lettere, ad esempio `zh-Hans` per il cinese (semplificato).

> [!NOTE]
> Per informazioni sulla creazione di file di risorse, vedere [Creazione di file di risorse](creating-resource-files-for-desktop-apps.md) e [Creazione di assembly satellite](creating-satellite-assemblies-for-desktop-apps.md).

<a name="cpconpackagingdeployingresourcesanchor1"></a>

## <a name="the-resource-fallback-process"></a>Processo di fallback per le risorse

Il modello hub e spoke di creazione dei pacchetti e distribuzione delle risorse usa un processo di fallback per trovare le risorse appropriate. Se in un'applicazione viene richiesta una risorsa localizzata non disponibile, tramite Common Language Runtime viene cercata nella gerarchia delle impostazioni cultura una risorsa di fallback appropriata che corrisponda il più possibile alla richiesta dell'applicazione dell'utente e viene generata un'eccezione solo come ultima soluzione. A ogni livello della gerarchia, quando viene trovata una risorsa appropriata viene usata tale risorsa. Se la ricerca ha esito negativo si passa al livello successivo.

Per migliorare le prestazioni di ricerca, applicare l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute> all'assembly principale e passare a tale attributo il nome della lingua neutra da usare con l'assembly principale.

### <a name="net-framework-resource-fallback-process"></a>Processo di fallback per le risorse di .NET Framework

Il processo di fallback per le risorse di .NET Framework include i passaggi seguenti:

> [!TIP]
> Potrebbe essere possibile usare l' [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) elemento di configurazione per ottimizzare il processo di fallback delle risorse e il processo mediante il quale il runtime esegue il probe degli assembly di risorse. Per altre informazioni vedere la sezione [Ottimizzazione del processo di fallback delle risorse](packaging-and-deploying-resources-in-desktop-apps.md#Optimizing).

1. Il runtime ricerca nella [Global Assembly Cache](../app-domains/gac.md) un assembly corrispondente alle impostazioni cultura richieste per l'applicazione.

     La Global Assembly Cache può archiviare assembly di risorse condivisi da più applicazioni. In tal modo non è necessario includere set di risorse specifici nella struttura di directory di ogni applicazione creata. Se il runtime rileva un riferimento all'assembly, cerca nell'assembly la risorsa richiesta. Se rileva la voce nell'assembly usa la risorsa richiesta. Se la voce non viene trovata la ricerca continua.

2. Il runtime cerca quindi nella directory dell'assembly in esecuzione una sottodirectory corrispondente alle impostazioni cultura richieste. Se trova la sottodirectory, cerca nella sottodirectory un assembly satellite valido per le impostazioni cultura richieste. Il runtime cerca quindi nell'assembly satellite la risorsa richiesta. Se trova la risorsa nell'assembly la usa direttamente. In caso contrario la ricerca continua.

3. Il runtime esegue una query in Windows Installer per determinare se l'assembly satellite va installato su richiesta. In tal caso il runtime gestisce l'installazione, carica l'assembly e cerca la risorsa richiesta. Se trova la risorsa nell'assembly la usa direttamente. In caso contrario la ricerca continua.

4. Il runtime genera l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per indicare che l'assembly satellite non è stato trovato. Se si sceglie di gestire l'evento, il gestore eventi può restituire un riferimento all'assembly satellite le cui risorse verranno usate per la ricerca. In caso contrario il gestore eventi restituisce `null` e la ricerca continua.

5. Il runtime torna a eseguire una ricerca nella Global Assembly Cache, ma ora cerca l'assembly padre delle impostazioni cultura richieste. Se l'assembly padre esiste nella Global Assembly Cache il runtime cerca nell'assembly la risorsa richiesta.

     Le impostazioni cultura padre sono definite come impostazioni cultura di fallback appropriate. Gli elementi padre sono candidati ideali per il fallback, perché l'impostazione di una risorsa qualsiasi è preferibile alla generazione di un'eccezione. Questo processo consente anche di tornare a usare le risorse. Una determinata risorsa va inclusa nel livello padre solo se le impostazioni cultura figlio non richiedono la localizzazione della risorsa richiesta. Se ad esempio si specificano assembly satellite per `en` (inglese neutro), `en-GB` (inglese del Regno Unito) ed `en-US` (inglese degli Stati Uniti), il satellite `en` contiene la terminologia comune, mentre i satelliti `en-GB` ed `en-US` possono fornire override solo per i termini diversi.

6. Il runtime cerca quindi nella directory dell'assembly in esecuzione una directory padre. Se esiste una directory padre il runtime cerca in tale directory un assembly satellite valido per le impostazioni cultura padre. Se il runtime trova l'assembly cerca nell'assembly la risorsa richiesta. Se trova la risorsa la usa direttamente. In caso contrario la ricerca continua.

7. Il runtime esegue una query in Windows Installer per determinare se l'assembly satellite padre va installato su richiesta. In tal caso il runtime gestisce l'installazione, carica l'assembly e cerca la risorsa richiesta. Se trova la risorsa nell'assembly la usa direttamente. In caso contrario la ricerca continua.

8. Il runtime genera l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> per indicare che non è stata trovata una risorsa di fallback appropriata. Se si sceglie di gestire l'evento, il gestore eventi può restituire un riferimento all'assembly satellite le cui risorse verranno usate per la ricerca. In caso contrario il gestore eventi restituisce `null` e la ricerca continua.

9. Il runtime esegue quindi la ricerca negli assembly padre come nei tre passaggi precedenti, su numerosi livelli potenziali. Ogni set di impostazioni cultura ha un solo set padre, definito dalla proprietà <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>, ma un set padre può a sua volta avere un proprio set padre. La ricerca di impostazioni cultura padre si interrompe quando la proprietà <xref:System.Globalization.CultureInfo.Parent%2A> di un set di impostazioni cultura restituisce <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Ai fini del fallback delle risorse le impostazioni cultura invariabili non sono considerate impostazioni cultura padre o impostazioni cultura che possono avere risorse.

10. Se dopo la ricerca nelle impostazioni cultura specificate in origine e in tutte le impostazioni cultura padre la risorsa non è stata trovata, viene usata la risorsa corrispondente alle impostazioni cultura predefinite (fallback). In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione. Tuttavia è possibile specificare il valore <xref:System.Resources.UltimateResourceFallbackLocation.Satellite> per la proprietà <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> dell'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute> per indicare come posizione finale di fallback per le risorse un assembly satellite anziché l'assembly principale.

    > [!NOTE]
    > La risorsa predefinita è l'unica risorsa che può essere compilata con l'assembly principale. Se non si specifica un assembly satellite tramite l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute>, la risorsa predefinita è il fallback finale (padre finale). È pertanto consigliabile includere sempre un set di risorse predefinito nell'assembly principale. Ciò evita la generazione di eccezioni. Se si include un file di risorse predefinito, si offre un fallback per tutte le risorse e si garantisce che l'utente disponga di almeno una risorsa, anche se questa non è specifica per le impostazioni cultura.

11. Infine se il runtime non trova una risorsa per impostazioni cultura predefinite (fallback) viene generata un'eccezione <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException> per indicare che la risorsa non è stata trovata.

Si supponga ad esempio che l'applicazione richieda una risorsa localizzata in spagnolo (Messico) (impostazioni cultura `es-MX`). Il runtime cerca nella Global Assembly Cache l'assembly corrispondente a `es-MX`, ma non lo trova. Il runtime cerca quindi nella directory dell'assembly in esecuzione una directory `es-MX`. Se la ricerca non ha esito positivo, il runtime cerca nuovamente nella Global Assembly Cache un assembly padre corrispondente alle impostazioni cultura di fallback, in questo esempio `es` (spagnolo). Se l'assembly padre non viene trovato, il runtime cerca le impostazioni cultura `es-MX` in tutti i livelli potenziali di assembly padre finché non trova una risorsa corrispondente. Se non trova una risorsa, il runtime usa la risorsa delle impostazioni cultura predefinite.

<a name="Optimizing"></a>

#### <a name="optimizing-the-net-framework-resource-fallback-process"></a>Ottimizzazione del processo di fallback per le risorse di .NET Framework

Se si verificano le seguenti condizioni, è possibile ottimizzare il processo con il quale il runtime cerca risorse negli assembly satellite

- Gli assembly satellite vengono distribuiti nello stesso percorso in cui si trova l'assembly di codice. Se l'assembly di codice è installato nella [Global Assembly Cache](../app-domains/gac.md) anche gli assembly satellite vengono installati nella Global Assembly Cache. Se l'assembly di codice è installato in una directory gli assembly satellite vengono installati in cartelle specifiche della directory, corrispondenti alle impostazioni cultura.

- Gli assembly satellite non vengono installati su richiesta.

- Il codice dell'applicazione non gestisce l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

È possibile ottimizzare il probe per gli assembly satellite includendo l' [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) elemento e impostando il relativo `enabled` attributo su `true` nel file di configurazione dell'applicazione, come illustrato nell'esempio seguente.

```xml
<configuration>
   <runtime>
      <relativeBindForResources enabled="true" />
   </runtime>
</configuration>
```

Il probe ottimizzato per gli assembly satellite è una funzionalità che richiede il consenso esplicito. In altre termini, il runtime segue i passaggi descritti nel [processo di fallback delle risorse](packaging-and-deploying-resources-in-desktop-apps.md#cpconpackagingdeployingresourcesanchor1) , a meno che l' [\<relativeBindForResources>](../configure-apps/file-schema/runtime/relativebindforresources-element.md) elemento non sia presente nel file di configurazione dell'applicazione e il relativo `enabled` attributo sia impostato su `true` . In questo caso il processo di probe di un assembly satellite viene modificato come segue:

- Il runtime usa il percorso dell'assembly del codice padre per il probe dell'assembly satellite. Se l'assembly padre è installato nella Global Assembly Cache il runtime esegue il probe nella cache ma non nella directory dell'applicazione. Se l'assembly padre è installato in una directory dell'applicazione il runtime esegue il probe nella directory dell'applicazione ma non nella Global Assembly Cache.

- Il runtime non esegue una query in Windows Installer per l'installazione su richiesta di assembly satellite.

- Se il probe per un assembly di risorse specifico non riesce, il runtime non genera l'evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

### <a name="net-core-resource-fallback-process"></a>Processo di fallback per le risorse di .NET Core

Il processo di fallback per le risorse di .NET Core include i passaggi seguenti:

1. Il runtime prova a caricare un assembly satellite per le impostazioni cultura richieste.
     - Cerca quindi nella directory dell'assembly in esecuzione una sottodirectory corrispondente alle impostazioni cultura richieste. Se trova la sottodirectory, cerca nella sottodirectory un assembly satellite valido per le impostazioni cultura richieste e lo carica.

       > [!NOTE]
       > Nei sistemi operativi con file system che fanno distinzione tra maiuscole e minuscole, ovvero Linux e macOS, la ricerca di sottodirectory con il nome delle impostazioni cultura fa distinzione tra maiuscole e minuscole. L'uso di maiuscole e minuscole nel nome della sottodirectory deve corrispondere esattamente a quello di <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, ad esempio `es` o `es-MX`.

       > [!NOTE]
       > Se il programmatore ha derivato un contesto di caricamento dell'assembly personalizzato da <xref:System.Runtime.Loader.AssemblyLoadContext>, la situazione è più complicata. Se l'assembly in esecuzione è stato caricato nel contesto personalizzato, il runtime carica l'assembly satellite nel contesto personalizzato. I dettagli esulano dall'ambito di questo documento. Vedere <xref:System.Runtime.Loader.AssemblyLoadContext>.

     - Se non viene trovato un assembly satellite, <xref:System.Runtime.Loader.AssemblyLoadContext> genera l'evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> per indicare che non riesce a trovare l'assembly. Se si sceglie di gestire l'evento, il gestore eventi può caricare e restituire un riferimento all'assembly satellite.
     - Se l'assembly satellite non viene ancora trovato, AssemblyLoadContext determina l'attivazione di un evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> da parte di AppDomain per indicare che non riesce a trovare l'assembly. Se si sceglie di gestire l'evento, il gestore eventi può caricare e restituire un riferimento all'assembly satellite.

2. Se non viene trovato un assembly satellite, il runtime cerca la risorsa richiesta. Se trova la risorsa nell'assembly la usa direttamente. In caso contrario la ricerca continua.

     > [!NOTE]
     > Per trovare una risorsa all'interno dell'assembly satellite, il runtime cerca il file di risorse richiesto da <xref:System.Resources.ResourceManager> per la proprietà <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> corrente. All'interno del file di risorse cerca il nome della risorsa richiesta. Se uno dei due non viene trovato, la risorsa viene considerata come non trovata.

3. Il runtime cerca quindi gli assembly di impostazioni cultura padre su molti livelli potenziali, ripetendo ogni ora i passaggi 1 e 2.

     Le impostazioni cultura padre sono definite come impostazioni cultura di fallback appropriate. Gli elementi padre sono candidati ideali per il fallback, perché l'impostazione di una risorsa qualsiasi è preferibile alla generazione di un'eccezione. Questo processo consente anche di tornare a usare le risorse. Una determinata risorsa va inclusa nel livello padre solo se le impostazioni cultura figlio non richiedono la localizzazione della risorsa richiesta. Se ad esempio si specificano assembly satellite per `en` (inglese neutro), `en-GB` (inglese del Regno Unito) ed `en-US` (inglese degli Stati Uniti), il satellite `en` contiene la terminologia comune, mentre i satelliti `en-GB` ed `en-US` forniscono override solo per i termini diversi.

     Ogni set di impostazioni cultura ha un solo set padre, definito dalla proprietà <xref:System.Globalization.CultureInfo.Parent%2A?displayProperty=nameWithType>, ma un set padre può a sua volta avere un proprio set padre. La ricerca di impostazioni cultura padre si arresta quando la proprietà <xref:System.Globalization.CultureInfo.Parent%2A> di un set di impostazioni cultura restituisce <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Ai fini del fallback delle risorse, le impostazioni cultura inglese non dipendenti da paese/area geografica non sono considerate impostazioni cultura padre o impostazioni cultura che possono avere risorse.

4. Se dopo la ricerca nelle impostazioni cultura specificate in origine e in tutte le impostazioni cultura padre la risorsa non è stata trovata, viene usata la risorsa corrispondente alle impostazioni cultura predefinite (fallback). In genere le risorse delle impostazioni cultura predefinite sono incluse nell'assembly principale dell'applicazione. È tuttavia possibile specificare il valore <xref:System.Resources.UltimateResourceFallbackLocation.Satellite?displayProperty.nameWithType> per la proprietà <xref:System.Resources.NeutralResourcesLanguageAttribute.Location%2A> per indicare che la posizione finale di fallback per le risorse è un assembly satellite anziché l'assembly principale.

    > [!NOTE]
    > La risorsa predefinita è l'unica risorsa che può essere compilata con l'assembly principale. Se non si specifica un assembly satellite tramite l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute>, la risorsa predefinita è il fallback finale (padre finale). È pertanto consigliabile includere sempre un set di risorse predefinito nell'assembly principale. Ciò evita la generazione di eccezioni. Se si include un file di risorse predefinito, si offre un fallback per tutte le risorse e si garantisce che l'utente disponga di almeno una risorsa, anche se questa non è specifica per le impostazioni cultura.

5. Se infine il runtime non trova un file di risorse per impostazioni cultura predefinite (fallback), viene generata un'eccezione <xref:System.Resources.MissingManifestResourceException> o <xref:System.Resources.MissingSatelliteAssemblyException> per indicare che la risorsa non è stata trovata. Se il file di risorse viene trovato ma la risorsa richiesta non è presente, la richiesta restituisce `null`.

### <a name="ultimate-fallback-to-satellite-assembly"></a>Fallback finale a un assembly satellite

Se si vuole è possibile rimuovere risorse dall'assembly principale e specificare che il runtime caricherà le risorse di fallback finale da un assembly satellite corrispondente a impostazioni cultura specifiche. Per controllare il processo di fallback si usa il costruttore <xref:System.Resources.NeutralResourcesLanguageAttribute.%23ctor%28System.String%2CSystem.Resources.UltimateResourceFallbackLocation%29> e si specifica un valore per il parametro <xref:System.Resources.UltimateResourceFallbackLocation> che indica se Resource Manager estrarrà le risorse di fallback dall'assembly principale o da un assembly satellite.

Nell'esempio di .NET Framework seguente viene usato l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute> per archiviare le risorse di fallback di un'applicazione in un assembly satellite per la lingua francese (`fr`). L'esempio include due file di testo di risorse che definiscono un'unica risorsa stringa denominata `Greeting`. Il primo file, resources.fr.txt, contiene una risorsa per la lingua francese.

```text
Greeting=Bon jour!
```

Il secondo file, resources.ru.txt, contiene una risorsa per la lingua russa.

```text
Greeting=Добрый день
```

Questi due file vengono compilati in file resources eseguendo il [generatore di file di risorse (Resgen.exe)](../tools/resgen-exe-resource-file-generator.md) dalla riga di comando. Per la risorsa di lingua francese il comando è:

**resgen.exe resources.fr.txt**

Per la risorsa di lingua russa il comando è:

**resgen.exe resources.ru.txt**

È possibile incorporare i file resources in librerie di collegamento dinamico (DLL) eseguendo [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) dalla riga di comando con la seguente sintassi per la risorsa di lingua francese:

**al /t:lib /embed:resources.fr.resources /culture:fr /out:fr\Example1.resources.dll**

e con la seguente sintassi per la risorsa di lingua russa:

**al /t:lib /embed:resources.ru.resources /culture:ru /out:ru\Example1.resources.dll**

Il codice sorgente dell'applicazione si trova in un file con nome Example1.cs o Example1.vb. Include l'attributo <xref:System.Resources.NeutralResourcesLanguageAttribute> per indicare che la risorsa di applicazione predefinita si trova nella sottodirectory fr. Crea un'istanza di Resource Manager, recupera il valore della risorsa `Greeting` e lo visualizza nella console.

[!code-csharp[Conceptual.Resources.Packaging#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.resources.packaging/cs/example1.cs#1)]
[!code-vb[Conceptual.Resources.Packaging#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.resources.packaging/vb/example1.vb#1)]

È quindi possibile compilare il codice sorgente C# dalla riga di comando come segue:

```console
csc Example1.cs
```

Il comando per il compilatore Visual Basic è molto simile:

```console
vbc Example1.vb
```

Poiché nell'assembly principale non sono incorporate risorse, non è necessario compilare con l'opzione `/resource`.

Quando si esegue l'esempio da un sistema la cui lingua è diversa dal russo viene visualizzato il seguente output:

```output
Bon jour!
```

## <a name="suggested-packaging-alternative"></a>Proposta alternativa per la creazione dei pacchetti

Vincoli di tempo o di budget potrebbero rendere difficile la creazione di un set di risorse per ogni subset di impostazioni cultura supportato dall'applicazione. In alternativa è possibile creare un solo assembly satellite per impostazioni cultura padre usabili da tutte le impostazioni cultura secondarie correlate. Ad esempio è possibile offrire un singolo assembly satellite inglese (en) che viene recuperato da utenti che richiedono risorse di regioni specifiche di lingua inglese e un singolo assembly satellite tedesco (de) per gli utenti che richiedono risorse di regioni specifiche di lingua tedesca. Le richieste per il tedesco parlato in Germania (de-DE), in Austria (de-AT) e in Svizzera (de-CH) avranno come fallback l'assembly satellite tedesco (de). Le risorse predefinite sono il fallback finale e come tali sono quelle richieste dalla maggior parte degli utenti dell'applicazione, perciò vanno scelte con attenzione. Questo approccio consente di distribuire risorse meno specifiche a livello di impostazioni cultura, ma in grado di ridurre notevolmente i costi di localizzazione dell'applicazione.

## <a name="see-also"></a>Vedere anche

- [Risorse nelle applicazioni desktop](index.md)
- [Global Assembly Cache](../app-domains/gac.md)
- [Creazione dei file di risorsa](creating-resource-files-for-desktop-apps.md)
- [Creazione di assembly satellite](creating-satellite-assemblies-for-desktop-apps.md)
