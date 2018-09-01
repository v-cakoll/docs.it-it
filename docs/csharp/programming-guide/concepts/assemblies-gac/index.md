---
title: Assembly e Global Assembly Cache (C#)
ms.date: 07/20/2015
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
ms.openlocfilehash: 07ee54fc19abecba5e8335f063277418ede80b36
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408918"
---
# <a name="assemblies-and-the-global-assembly-cache-c"></a>Assembly e Global Assembly Cache (C#)
Gli assembly costituiscono l'unità fondamentale della distribuzione, del controllo delle versioni, del riutilizzo, dell'ambito di attivazione e delle autorizzazioni di sicurezza per un'applicazione basata su .NET. Gli assembly hanno il formato di un file eseguibile (con estensione exe) o di libreria a collegamento dinamico (con estensione dll) e costituiscono i blocchi predefiniti di .NET Framework. Gli assembly forniscono al Common Language Runtime le informazioni necessarie per riconoscere le implementazioni dei tipi. Un assembly può essere considerato come una raccolta di tipi e risorse che formano un'unità logica di funzionalità e che sono creati per interagire.  
  
 Gli assembly possono contenere uno o più moduli. È ad esempio possibile pianificare i progetti di grandi dimensioni in modo tale che diversi sviluppatori lavorino su moduli distinti che, una volta raggruppati, costituiranno un singolo assembly. Per altre informazioni sui moduli, vedere l'argomento [Procedura: Compilare un assembly su più file](../../../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md).  
  
 Di seguito sono riportate le proprietà degli assembly:  
  
-   Gli assembly vengono implementati come file con estensione exe o dll.  
  
-   È possibile condividere un assembly tra più applicazioni inserendolo nella Global Assembly Cache. Prima di inserirlo nella Global Assembly Cache, è necessario assegnare a un assembly un nome sicuro. Per altre informazioni, vedere [Assembly con nomi sicuri](../../../../../docs/framework/app-domains/strong-named-assemblies.md).  
  
-   Gli assembly vengono caricati in memoria solo se sono richiesti. Se non sono usati, non vengono caricati. Questo significa che gli assembly rappresentano un modo efficace per gestire le risorse nei progetti di maggiori dimensioni.  
  
-   È possibile ottenere informazioni su un assembly a livello di codice tramite reflection. Per altre informazioni, vedere [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
-   Per caricare un assembly solo per esaminarlo, usare un metodo come <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>.  
  
## <a name="assembly-manifest"></a>Manifesto dell'assembly  
 All'interno di ogni assembly è presente un *manifesto dell'assembly*. Il manifesto dell'assembly è simile a un indice e contiene quanto segue:  
  
-   L'identità dell'assembly, ovvero il nome e la versione.  
  
-   Una tabella di file in cui sono descritti tutti gli altri file che costituiscono l'assembly, ad esempio eventuali altri assembly creati su cui si basano il file con estensione exe o dll o anche i file bitmap o Readme.  
  
-   Un *elenco di riferimenti all'assembly*, ovvero un elenco di tutte le dipendenze esterne. Può trattarsi di file con estensione dll o di altri file richiesti dall'applicazione e che possono essere creati da altri sviluppatori. I riferimenti all'assembly contengono riferimenti a oggetti sia privati che globali. Gli oggetti globali si trovano nella Global Assembly Cache, una zona disponibile per altre applicazioni. Gli oggetti privati devono trovarsi in una directory di livello pari o inferiore a quello della directory nella quale è installata l'applicazione.  
  
 Poiché gli assembly contengono informazioni sul contenuto, sul controllo delle versioni e sulle dipendenze, per funzionare in modo corretto le applicazioni create con C# non si basano sui valori del Registro di sistema di Windows. Gli assembly riducono i conflitti tra file con estensione dll e rendono le applicazioni più affidabili e facili da distribuire. In molti casi, è possibile installare un'applicazione basata su .NET semplicemente copiandone i file nel computer di destinazione.  
  
 Per altre informazioni, vedere [Manifesto dell'assembly](../../../../../docs/framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Aggiunta di un riferimento a un assembly  
 Per usare un assembly, è necessario aggiungervi un riferimento. Successivamente, usare la [direttiva using](../../../../csharp/language-reference/keywords/using-directive.md) per scegliere lo spazio dei nomi degli elementi da usare. Dopo che l'utente ha fatto riferimento a un assembly e lo ha importato, tutte le classi, le proprietà, i metodi e gli altri membri accessibili dei relativi spazi dei nomi risulteranno disponibili per l'applicazione, come se il relativo codice facesse parte del file di origine.  
  
 In C# è anche possibile usare due versioni dello stesso assembly in una singola applicazione. Per altre informazioni, vedere [alias esterno](../../../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Creazione di un assembly  
 Compilare l'applicazione facendo clic su **Compila** nel menu **Compila** oppure usando il compilatore della riga di comando. Per informazioni dettagliate sulla compilazione degli assembly dalla riga di comando, vedere [Compilazione dalla riga di comando con csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
> [!NOTE]
>  Per compilare un assembly in Visual Studio, scegliere **Compila** dal menu **Compila**.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../../csharp/programming-guide/index.md)  
 [Assembly in Common Language Runtime](../../../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [Assembly Friend (C#)](friend-assemblies.md)  
 [Procedura: Condividere un assembly con altre applicazioni (C#)](how-to-share-an-assembly-with-other-applications.md)  
 [Procedura: Caricare e scaricare gli assembly (C#)](how-to-load-and-unload-assemblies.md)  
 [Procedura: Determinare se un file è un assembly (C#)](how-to-determine-if-a-file-is-an-assembly.md)  
 [Procedura: Creare e usare assembly dalla riga di comando (C#)](how-to-create-and-use-assemblies-using-the-command-line.md)  
 [Procedura dettagliata: Incorporamento dei tipi da assembly gestiti in Visual Studio (C#)](walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)  
 [Procedura dettagliata: Incorporamento delle informazioni sui tipi da assembly di Microsoft Office in Visual Studio (C#)](walkthrough-embedding-type-information-from-microsoft-office-assemblies.md)
