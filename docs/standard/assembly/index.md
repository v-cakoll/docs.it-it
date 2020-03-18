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
ms.openlocfilehash: f85fef37ac952c91ac73570f26d80d8a46f4eedf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156505"
---
# <a name="assemblies-in-net"></a>Assembly in .NET

Gli assembly costituiscono le unità fondamentali di distribuzione, controllo della versione, riutilizzo, ambito di attivazione e autorizzazioni di sicurezza per . applicazioni basate su rete. Un assembly è una raccolta di tipi e risorse creati per essere usati insieme e per formare un'unità logica di funzionalità. Gli assembly assumono la forma di file eseguibili (*.exe*) o di libreria a collegamento dinamico (*DLL*) e sono i blocchi predefiniti delle applicazioni .NET. Gli assembly forniscono al Common Language Runtime le informazioni necessarie per riconoscere le implementazioni dei tipi.

In .NET Core e .NET Framework è possibile compilare un assembly da uno o più file di codice sorgente. In .NET Framework gli assembly possono contenere uno o più moduli. Ciò consente di pianificare progetti di grandi dimensioni in modo che diversi sviluppatori possano lavorare su moduli o file di codice sorgente separati, combinati per creare un singolo assembly. Per ulteriori informazioni sui moduli, vedere [Procedura: compilare un assembly su più file](../../framework/app-domains/build-multifile-assembly.md).

Di seguito sono riportate le proprietà degli assembly:

- Gli assembly vengono implementati come file *con estensione exe* o *dll.*

- Per le librerie destinate a .NET Framework, è possibile condividere assembly tra applicazioni inserendoli nella [Global Assembly Cache (GAC)](../../framework/app-domains/gac.md). È necessario assegnare un nome sicuro agli assembly prima di poterli includere nella Global Assembly Cache. Per ulteriori informazioni, vedere [Assembly con nome sicuro](strong-named.md).

- Gli assembly vengono caricati in memoria solo se sono richiesti. Se non vengono utilizzati, non vengono caricati. Questo significa che gli assembly rappresentano un modo efficace per gestire le risorse nei progetti di maggiori dimensioni.

- È possibile ottenere informazioni su un assembly a livello di codice tramite reflection. Per altre informazioni, vedere [Reflection (C#)](../../csharp/programming-guide/concepts/reflection.md) o [Reflection (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- È possibile caricare un assembly solo <xref:System.Reflection.MetadataLoadContext> per esaminarlo utilizzando <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> la <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType> classe in .NET Core e i metodi or in .NET Core e .NET Framework.

## <a name="assemblies-in-the-common-language-runtime"></a>Assembly in Common Language Runtime

Gli assembly forniscono a Common Language Runtime le informazioni necessarie per conoscere le implementazioni del tipo. Per il runtime, un tipo non esiste all'esterno del contesto di un assembly.

Un assieme definisce le seguenti informazioni:

- Codice eseguito da Common Language Runtime. Si noti che ogni assieme `DllMain`può `WinMain`avere `Main`un solo punto di ingresso: , , o .

- Limite di sicurezza. Un assembly è l'unità presso cui sono richieste e concesse le autorizzazioni. Per ulteriori informazioni sui limiti di sicurezza negli assembly, vedere [Considerazioni sulla sicurezza degli assembly](security-considerations.md).

- Digitare il contorno. L'identità di ogni tipo include il nome dell'assembly in cui risiede. Un tipo con nome `MyType` caricato nell'ambito di un assembly è diverso da un tipo con nome `MyType` caricato nell'ambito di un altro assembly.

- Limite dell'ambito di riferimento. Il [manifesto dell'assembly](#assembly-manifest) contiene metadati utilizzati per la risoluzione dei tipi e la soddisfazione delle richieste di risorse. Il manifesto specifica i tipi e le risorse da esporre all'esterno dell'assembly ed enumera gli altri assembly da cui dipende. Il codice MSIL (Microsoft Intermediate Language) in un file eseguibile portabile (PE) non verrà eseguito a meno che non disponga di un [manifesto assembly](#assembly-manifest)associato.

- Limite di versione. L'assembly è l'unità versionable più piccola in Common Language Runtime. Tutti i tipi e le risorse nello stesso assembly vengono sottoposti a controllo delle versioni come unità. Il [manifesto dell'assembly](#assembly-manifest) descrive le dipendenze di versione specificate per tutti gli assembly dipendenti. Per ulteriori informazioni sul controllo delle versioni, vedere [Controllo delle versioni degli assembly](versioning.md).

- Unità di distribuzione. All'avvio di un'applicazione, devono essere presenti solo gli assembly chiamati inizialmente dall'applicazione. Altri assembly, ad esempio assembly contenenti risorse di localizzazione o classi di utilità, possono essere recuperati su richiesta. Ciò consente alle app di essere semplici e sottili quando vengono scaricate per la prima volta. Per ulteriori informazioni sulla distribuzione di assembly, vedere [Distribuire applicazioni](../../framework/deployment/index.md).

- Unità di esecuzione affiancata. Per ulteriori informazioni sull'esecuzione di più versioni di un assembly, vedere [Assembly ed esecuzione side-by-side](side-by-side-execution.md).

## <a name="create-an-assembly"></a>Creare un assieme

Gli assembly possono essere statici o dinamici. Gli assembly statici sono archiviati su disco in file eseguibili portabili. Gli assembly statici possono includere interfacce, classi e risorse come bitmap, file JPEG e altri file di risorse. È inoltre possibile creare assembly dinamici, che vengono eseguiti direttamente dalla memoria e non vengono salvati su disco prima dell'esecuzione. È possibile salvare gli assembly dinamici su disco dopo l'esecuzione.

Esistono diversi modi per creare assembly. È possibile utilizzare gli strumenti di sviluppo, ad esempio Visual Studio, che possono creare file *DLL* o *EXE.* È possibile utilizzare gli strumenti di Windows SDK per creare assembly con moduli da altri ambienti di sviluppo. Per creare assembly dinamici è anche possibile usare le API di Common Language Runtime come <xref:System.Reflection.Emit?displayProperty=nameWithType>.

Compilare gli assembly compilandoli in Visual Studio, compilandoli con gli strumenti dell'interfaccia della riga di comando di .NET Core o compilando assembly .NET Framework con un compilatore da riga di comando. Per altre informazioni sulla compilazione di assembly tramite l'interfaccia della riga di comando di .NET Core, vedere Panoramica dell'interfaccia della riga di comando di [.NET Core .NET Core .NET Core](../../core/tools/index.md). Per la compilazione di assembly con i compilatori da riga di comando, vedere Compilazione da riga di [comando con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) per C ' o [Compilazione dalla riga](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) di comando per Visual Basic.

> [!NOTE]
> Per compilare un assembly in Visual Studio, scegliere **Compila**dal menu **Compila** .

## <a name="assembly-manifest"></a>Manifesto dell'assembly

Ogni assembly dispone di un file *manifesto dell'assembly.* Analogamente a un sommario, il manifesto dell'assembly contiene:

- L'identità dell'assembly, ovvero il nome e la versione.

- Tabella di file che descrive tutti gli altri file che costituiscono l'assembly, ad esempio altri assembly creati su cui si basa il file *con estensione exe* o *dll,* i file bitmap o i file Readme.

- Un elenco di *riferimenti all'assembly*, che è un elenco di tutte le dipendenze esterne, ad esempio *DLL*o altri file. I riferimenti all'assembly contengono riferimenti a oggetti sia privati che globali. Gli oggetti globali sono disponibili per tutte le altre applicazioni. In .NET Core gli oggetti globali vengono associati a un runtime .NET Core specifico. In .NET Framework gli oggetti globali risiedono nella Global Assembly Cache (GAC). *System.IO.dll* è un esempio di assembly nella Global Assembly Cache. Gli oggetti privati devono trovarsi a livello di directory a o al di sotto della directory in cui è installata l'app.

Poiché gli assembly contengono informazioni sul contenuto, il controllo delle versioni e le dipendenze, le applicazioni che li utilizzano non devono basarsi su origini esterne, ad esempio il Registro di sistema nei sistemi Windows, per funzionare correttamente. Gli assembly riducono i conflitti *con estensione dll* e rendono le applicazioni più affidabili e facili da distribuire. In molti casi, è possibile installare un'applicazione basata su .NET semplicemente copiandone i file nel computer di destinazione. Per ulteriori informazioni, vedere [Manifesto dell'assembly](manifest.md).

## <a name="add-a-reference-to-an-assembly"></a>Aggiungere un riferimento a un assembly

Per utilizzare un assembly in un'applicazione, è necessario aggiungervi un riferimento. Una volta fatto riferimento a un assembly, tutti i tipi, le proprietà, i metodi e gli altri membri dei relativi spazi dei nomi accessibili sono disponibili per l'applicazione come se il codice facesse parte del file di origine.

> [!NOTE]
> Per la maggior parte degli assembly dalla libreria di classi .NET i riferimenti sono automatici. Se non viene fatto automaticamente riferimento a un assembly di sistema, per .NET Core è possibile aggiungere un riferimento al pacchetto NuGet che contiene l'assembly. Utilizzare Gestione pacchetti NuGet in Visual Studio [ \<](../../core/tools/dependencies.md#the-packagereference-element) oppure aggiungere un elemento di>PackageReference per l'assembly al progetto *con estensione csproj* o *vbproj.* In .NET Framework è possibile aggiungere un riferimento all'assembly utilizzando la finestra `-reference` di dialogo Aggiungi **riferimento** in Visual Studio oppure l'opzione della riga di comando per i compilatori di Visual Basic o di [Visual](../../csharp/language-reference/compiler-options/reference-compiler-option.md) [Basic.](../../visual-basic/reference/command-line-compiler/reference.md)

Nel linguaggio c'è, è possibile utilizzare due versioni dello stesso assembly in una singola applicazione. Per altre informazioni, vedere [alias esterno](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="related-content"></a>Contenuti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Contenuto degli assembly](contents.md)|Elementi che costituiscono un assieme.|
|[Manifesto dell'assembly](manifest.md)|Dati nel manifesto dell'assembly e modalità di archiviazione negli assembly.|
|[Global Assembly Cache](../../framework/app-domains/gac.md)|Modalità di memorizzazione e utilizzo degli assembly da parte della Global Assembly Cache.|
|[Assembly con nome sicuro](strong-named.md)|Caratteristiche degli assembly con nome sicuro.|
|[Considerazioni sulla sicurezza degli assembly](security-considerations.md)|Funzionamento della sicurezza con gli assembly.|
|[Controllo delle versioni degli assembly](versioning.md)|Panoramica dei criteri di controllo delle versioni di .NET Framework.|
|[Posizionamento dell'assieme](../../framework/app-domains/assembly-placement.md)|Dove individuare gli assiemi.|
|[Assembly ed esecuzione contemporanea di più versioni](side-by-side-execution.md)|Utilizzare più versioni del runtime o un assembly contemporaneamente.|
|[Creare metodi e assembly dinamici](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Come creare assembly dinamici.|
|[Come il runtime individua gli assembly](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|Modalità di risoluzione dei riferimenti agli assembly in fase di esecuzione.|

## <a name="reference"></a>Informazioni di riferimento

<xref:System.Reflection.Assembly?displayProperty=nameWithType>

## <a name="see-also"></a>Vedere anche

- [Formato di file di assembly .NET](file-format.md)
- [Assembly Friend](friend.md)
- [Assembly di riferimento](reference-assemblies.md)
- [Procedura: caricare e scaricare assemblyHow to: Load and unload assemblies](load-unload.md)
- [Procedura: utilizzare ed eseguire il debug di un'assembly di scaricamento in .NET CoreHow to: Use and debug assembly unloadability in .NET Core](unloadability.md)
- [Procedura: determinare se un file è un assemblyHow to: Determine if a file is an assembly](identify.md)
