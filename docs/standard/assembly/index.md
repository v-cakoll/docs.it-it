---
title: Assembly in .NET
ms.date: 08/15/2019
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.openlocfilehash: 9fd0c55294815c191f1e116dd4e16a44693f3565
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900588"
---
# <a name="assemblies-in-net"></a>Assembly in .NET

Gli assembly costituiscono le unità di base per la distribuzione, il controllo della versione, il riutilizzo, l'ambito di attivazione e le autorizzazioni di sicurezza per. Applicazioni basate su rete. Un assembly è una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità. Gli assembly hanno la forma di file eseguibili (con*estensione exe*) o di libreria a collegamento dinamico (*dll*) e sono i blocchi predefiniti delle applicazioni .NET. Gli assembly forniscono al Common Language Runtime le informazioni necessarie per riconoscere le implementazioni dei tipi.

In .NET Core e .NET Framework è possibile compilare un assembly da uno o più file di codice sorgente. In .NET Framework gli assembly possono contenere uno o più moduli. In questo modo è possibile pianificare progetti di grandi dimensioni in modo che più sviluppatori possano lavorare su moduli o file di codice sorgente distinti, combinati per creare un singolo assembly. Per altre informazioni sui moduli, vedere [procedura: compilare un assembly](../../framework/app-domains/build-multifile-assembly.md)su più file.

Di seguito sono riportate le proprietà degli assembly:

- Gli assembly vengono implementati come file con *estensione exe* o *dll* .

- Per le librerie destinate alla .NET Framework, è possibile condividere gli assembly tra le applicazioni inserendoli nella [global assembly cache (GAC)](../../framework/app-domains/gac.md). Prima di poterli includere nella GAC, è necessario assegnare nomi sicuri agli assembly. Per ulteriori informazioni, vedere [assembly con nome sicuro](strong-named.md).

- Gli assembly vengono caricati in memoria solo se sono richiesti. Se non vengono usati, non vengono caricati. Questo significa che gli assembly rappresentano un modo efficace per gestire le risorse nei progetti di maggiori dimensioni.

- È possibile ottenere informazioni su un assembly a livello di codice tramite reflection. Per altre informazioni, vedere [Reflection (C#)](../../csharp/programming-guide/concepts/reflection.md) o [Reflection (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- È possibile caricare un assembly solo per esaminarlo usando la classe <xref:System.Reflection.MetadataLoadContext> in .NET Core e i metodi <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> in .NET Core e .NET Framework.

## <a name="assemblies-in-the-common-language-runtime"></a>Assembly nel Common Language Runtime

Gli assembly forniscono la Common Language Runtime con le informazioni necessarie per conoscere le implementazioni dei tipi. Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.

Un assembly definisce le seguenti informazioni:

- Codice eseguito dal Common Language Runtime. Si noti che ogni assembly può avere un solo punto di ingresso: `DllMain`, `WinMain`o `Main`.

- Limite di sicurezza. Un assembly è l'unità presso cui sono richieste e concesse le autorizzazioni. Per ulteriori informazioni sui limiti di sicurezza negli assembly, vedere [considerazioni sulla sicurezza degli assembly](security-considerations.md).

- Limite del tipo. L'identità di ogni tipo include il nome dell'assembly in cui risiede. Un tipo con nome `MyType` caricato nell'ambito di un assembly è diverso da un tipo con nome `MyType` caricato nell'ambito di un altro assembly.

- Limite dell'ambito di riferimento. Il [manifesto dell'assembly](#assembly-manifest) contiene metadati usati per risolvere i tipi e soddisfare le richieste di risorse. Il manifesto specifica i tipi e le risorse da esporre all'esterno dell'assembly ed enumera altri assembly da cui dipende. Il codice MSIL (Microsoft Intermediate Language) in un file eseguibile portabile (PE) non verrà eseguito a meno che non disponga di un [manifesto dell'assembly](#assembly-manifest)associato.

- Limite della versione. L'assembly è la più piccola unità di versione nella Common Language Runtime. Il controllo delle versioni di tutti i tipi e le risorse nello stesso assembly viene apposto come unità. Il [manifesto dell'assembly](#assembly-manifest) descrive le dipendenze della versione specificate per gli assembly dipendenti. Per ulteriori informazioni sul controllo delle versioni, vedere [controllo delle versioni degli assembly](versioning.md).

- Unità di distribuzione. All'avvio di un'applicazione, devono essere presenti solo gli assembly chiamati inizialmente dall'applicazione. Gli altri assembly, ad esempio gli assembly contenenti le risorse di localizzazione o le classi di utilità, possono essere recuperati su richiesta. In questo modo le app possono essere semplici e sottili quando vengono scaricati per la prima volta. Per ulteriori informazioni sulla distribuzione degli assembly, vedere [deploy Applications](../../framework/deployment/index.md).

- Unità di esecuzione side-by-side. Per ulteriori informazioni sull'esecuzione di più versioni di un assembly, vedere [assembly ed esecuzione side-by-side](side-by-side-execution.md).

## <a name="create-an-assembly"></a>Creazione di un assembly

Gli assembly possono essere statici o dinamici. Gli assembly statici sono archiviati su disco in file eseguibili portabili. Gli assembly statici possono includere interfacce, classi e risorse quali bitmap, file JPEG e altri file di risorse. È anche possibile creare assembly dinamici, eseguiti direttamente dalla memoria e non salvati su disco prima dell'esecuzione. È possibile salvare gli assembly dinamici su disco dopo l'esecuzione.

Esistono diversi modi per creare assembly. È possibile usare gli strumenti di sviluppo, ad esempio Visual Studio, che possono creare file con estensione *dll* o *exe* . È possibile usare gli strumenti nel Windows SDK per creare assembly con moduli da altri ambienti di sviluppo. Per creare assembly dinamici è anche possibile usare le API di Common Language Runtime come <xref:System.Reflection.Emit?displayProperty=nameWithType>.

Compila gli assembly in Visual Studio, creandoli con strumenti dell'interfaccia della riga di comando di .NET Core o compilando .NET Framework assembly con un compilatore da riga di comando. Per ulteriori informazioni sulla compilazione di assembly mediante gli strumenti dell'interfaccia della riga di comando di .NET Core, vedere [strumenti dell'interfaccia della riga di comando di .NET Core](../../core/tools/index.md). Per la compilazione di assembly con i compilatori della riga di comando, vedere [compilazione da riga di comando con csc. exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) per C#o [compilazione dalla riga di comando](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) per Visual Basic.

> [!NOTE]
> Per compilare un assembly in Visual Studio, scegliere **Compila**dal menu **Compila** .

## <a name="assembly-manifest"></a>Manifesto dell'assembly

Ogni assembly dispone di un file *manifesto dell'assembly* . Analogamente a un sommario, il manifesto dell'assembly contiene:

- L'identità dell'assembly, ovvero il nome e la versione.

- Una tabella di file che descrive tutti gli altri file che costituiscono l'assembly, ad esempio gli altri assembly creati per il file con estensione *exe* o *dll* , i file bitmap o i file Leggimi.

- *Elenco di riferimenti ad assembly*, ovvero un elenco di tutte le dipendenze esterne, ad esempio *. dll*o altri file. I riferimenti all'assembly contengono riferimenti a oggetti sia privati che globali. Gli oggetti globali sono disponibili per tutte le altre applicazioni. In .NET Core gli oggetti globali sono abbinati a un particolare runtime di .NET Core. In .NET Framework gli oggetti globali si trovano nella Global Assembly Cache (GAC). *System. io. dll* è un esempio di assembly nella GAC. Gli oggetti privati devono trovarsi in un livello di directory all'interno o al di sotto della directory in cui è installata l'app.

Poiché gli assembly contengono informazioni sul contenuto, sul controllo delle versioni e sulle dipendenze, le applicazioni che le utilizzano non devono basarsi su origini esterne, ad esempio il registro di sistema nei sistemi Windows, per funzionare correttamente. Gli assembly riducono i conflitti con *estensione dll* e rendono le applicazioni più affidabili e facili da distribuire. In molti casi, è possibile installare un'applicazione basata su .NET semplicemente copiandone i file nel computer di destinazione. Per altre informazioni, vedere [manifesto dell'assembly](manifest.md).

## <a name="add-a-reference-to-an-assembly"></a>Aggiungere un riferimento a un assembly

Per usare un assembly in un'applicazione, è necessario aggiungervi un riferimento. Quando si fa riferimento a un assembly, tutti i tipi accessibili, le proprietà, i metodi e gli altri membri dei relativi spazi dei nomi sono disponibili per l'applicazione come se il codice fosse parte del file di origine.

> [!NOTE]
> Per la maggior parte degli assembly dalla libreria di classi .NET i riferimenti sono automatici. Se non viene fatto automaticamente riferimento a un assembly di sistema, per .NET Core è possibile aggiungere un riferimento al pacchetto NuGet che contiene l'assembly. Usare Gestione pacchetti NuGet in Visual Studio o aggiungere un elemento [\<PackageReference >](../../core/tools/dependencies.md#the-new-packagereference-element) per l'assembly al progetto *. csproj* o *. vbproj* . In .NET Framework, è possibile aggiungere un riferimento all'assembly usando la finestra di dialogo **Aggiungi riferimento** in Visual Studio oppure usando l'opzione della riga di comando `-reference` per i [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) compilatori o [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md) .

In C#è possibile utilizzare due versioni dello stesso assembly in una singola applicazione. Per altre informazioni, vedere [alias esterno](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="related-content"></a>Contenuti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Contenuto dell'assembly](contents.md)|Elementi che costituiscono un assembly.|
|[Manifesto dell'assembly](manifest.md)|I dati nel manifesto dell'assembly e il modo in cui vengono archiviati negli assembly.|
|[Assembly Cache globale](../../framework/app-domains/gac.md)|Modalità di archiviazione e di utilizzo degli assembly nella GAC.|
|[Assembly con nomi sicuri](strong-named.md)|Caratteristiche degli assembly con nome sicuro.|
|[Considerazioni sulla sicurezza degli assembly](security-considerations.md)|Funzionamento della sicurezza con gli assembly.|
|[Controllo delle versioni degli assembly](versioning.md)|Panoramica dei criteri di controllo delle versioni .NET Framework.|
|[Posizionamento degli assembly](../../framework/app-domains/assembly-placement.md)|Posizione in cui individuare gli assembly.|
|[Assembly e esecuzione side-by-side](side-by-side-execution.md)|Usare più versioni del runtime o di un assembly simultaneamente.|
|[Creare assembly e metodi dinamici](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Come creare assembly dinamici.|
|[Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|Il modo in cui il .NET Framework risolve i riferimenti ad assembly in fase di esecuzione.|

## <a name="reference"></a>Riferimenti

<xref:System.Reflection.Assembly?displayProperty=nameWithType>

## <a name="see-also"></a>Vedere anche

- [Formato dei file di assembly .NET](file-format.md)
- [Assembly Friend](friend.md)
- [Assembly di riferimento](reference-assemblies.md)
- [Procedura: caricare e scaricare assembly](load-unload.md)
- [Procedura: usare ed eseguire il debug dello scaricamento di assembly in .NET Core](unloadability.md)
- [Procedura: determinare se un file è un assembly](identify.md)
