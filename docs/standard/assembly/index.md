---
title: Assembly in .NET
ms.date: 07/10/2018
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
---
# <a name="assemblies-in-net"></a>Assembly in .NET

Gli assembly costituiscono l'unità fondamentale della distribuzione, del controllo delle versioni, del riutilizzo, dell'ambito di attivazione e delle autorizzazioni di sicurezza per un'applicazione basata su .NET. Gli assembly hanno il formato di un file eseguibile (con estensione exe) o di libreria a collegamento dinamico (con estensione dll) e rappresentano i blocchi costitutivi delle applicazioni .NET. Gli assembly forniscono al Common Language Runtime le informazioni necessarie per riconoscere le implementazioni dei tipi. Un assembly può essere considerato come una raccolta di tipi e risorse che formano un'unità logica di funzionalità e che sono creati per interagire.  
  
 In .NET Core e .NET Framework un assembly può essere formato da uno o più file di codice sorgente. In .NET Framework gli assembly possono contenere uno o più moduli. Ciò consente di pianificare i progetti di grandi dimensioni in modo tale che diversi sviluppatori lavorino su file di codice sorgente o moduli distinti che vengono poi combinati per creare un singolo assembly. Per altre informazioni sui moduli, vedere [Procedura: Compilare un assembly con più file](../../framework/app-domains/how-to-build-a-multifile-assembly.md).
  
 Di seguito sono riportate le proprietà degli assembly:  
  
-   Gli assembly vengono implementati come file con estensione exe o dll.  
  
-   Per le librerie destinate a .NET Framework è possibile condividere un assembly tra più applicazioni inserendolo nella [Global Assembly Cache](../../framework/app-domains/gac.md). Prima di inserirlo nella Global Assembly Cache, è necessario assegnare a un assembly un nome sicuro. Per altre informazioni, vedere [Assembly con nomi sicuri](../../framework/app-domains/strong-named-assemblies.md).  
  
-   Gli assembly vengono caricati in memoria solo se sono richiesti. Se non sono usati, non vengono caricati. Questo significa che gli assembly rappresentano un modo efficace per gestire le risorse nei progetti di maggiori dimensioni.  
  
-   È possibile ottenere informazioni su un assembly a livello di codice tramite reflection. Per altre informazioni, vedere [Reflection (C#)](../../csharp/programming-guide/concepts/reflection.md) o [Reflection (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).   
  
-   È possibile caricare un assembly solo per esaminarlo chiamando il metodo <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>.  
  
## <a name="assembly-manifest"></a>Manifesto dell'assembly  
 All'interno di ogni assembly è presente un *manifesto dell'assembly*. Il manifesto dell'assembly è simile a un indice e contiene quanto segue:  
  
-   L'identità dell'assembly, ovvero il nome e la versione.  
  
-   Una tabella di file in cui sono descritti tutti gli altri file che costituiscono l'assembly, ad esempio eventuali altri assembly creati su cui si basano il file con estensione exe o dll o anche i file bitmap o Leggimi.  
  
-   Un *elenco di riferimenti all'assembly*, ovvero un elenco di tutte le dipendenze esterne. Può trattarsi di file con estensione dll o di altri file richiesti dall'applicazione e che possono essere creati da altri sviluppatori. I riferimenti all'assembly contengono riferimenti a oggetti sia privati che globali. Gli oggetti globali sono disponibili per tutte le altre applicazioni. In .NET Core essi sono associati a un determinato runtime di .NET Core. In .NET Framework risiedono nella Global Assembly Cache. Lo spazio dei nomi <xref:System.IO?displayProperty=nameWithType> è un esempio di assembly nella Global Assembly Cache. Gli oggetti privati devono trovarsi in una directory di livello pari o inferiore a quello della directory nella quale è installata l'applicazione.  
  
 Dato che gli assembly contengono informazioni sul contenuto, sul controllo delle versioni e sulle dipendenze, per funzionare in modo corretto le applicazioni che li usano non devono basarsi sui valori del Registro di sistema di Windows. Gli assembly riducono i conflitti tra file con estensione dll e rendono le applicazioni più affidabili e facili da distribuire. In molti casi, è possibile installare un'applicazione basata su .NET semplicemente copiandone i file nel computer di destinazione. Per altre informazioni, vedere [Manifesto dell'assembly](../../framework/app-domains/assembly-manifest.md).  
  
## <a name="adding-a-reference-to-an-assembly"></a>Aggiunta di un riferimento a un assembly  
 Per usare un assembly, è necessario aggiungervi un riferimento. È poi possibile usare la [direttiva using](../../csharp/language-reference/keywords/using-directive.md) per C# oppure l'[istruzione Imports](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per Visual Basic per scegliere lo spazio dei nomi degli elementi che si vuole usare. Dopo aver impostato un riferimento a un assembly e averlo importato, tutte le classi, le proprietà, i metodi e gli altri membri accessibili dei relativi spazi dei nomi risulteranno disponibili per l'applicazione, come se il relativo codice facesse parte del file di origine.  
 
> [!NOTE]
> Per la maggior parte degli assembly dalla libreria di classi .NET i riferimenti sono automatici. In alcuni casi, tuttavia, potrebbe non essere disponibile il riferimento automatico a un assembly di sistema. In .NET Core, è possibile aggiungere un riferimento al pacchetto NuGet che contiene l'assembly tramite Gestione pacchetti NuGet in Visual Studio o aggiungendo un elemento [<PackageReference>](../../core/tools/dependencies.md#the-new-packagereference-element) per l'assembly al progetto csproj o vbproj. In .NET Framework è possibile aggiungere un riferimento all'assembly tramite la finestra di dialogo **Aggiungi riferimento** in Visual Studio o tramite l'opzione della riga di comando `-reference` per i compilatori [ C# ](../../csharp/language-reference/compiler-options/reference-compiler-option.md) o [ Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md).
 
 In C# è anche possibile usare due versioni dello stesso assembly in una singola applicazione. Per altre informazioni, vedere [alias esterno](../../csharp/language-reference/keywords/extern-alias.md).  
  
## <a name="creating-an-assembly"></a>Creazione di un assembly  
 Compilare l'applicazione in Visual Studio, dalla riga di comando con gli strumenti dell'interfaccia della riga di comando di .NET Core o compilando assembly .NET Framework con un compilatore da riga di comando. Per altre informazioni sulla compilazione degli assembly usando gli strumenti dell'interfaccia della riga di comando .NET, vedere [Strumenti dell'interfaccia della riga di comando di .NET Core](../../core/tools/index.md). Per la compilazione di assembly con i compilatori della riga di comando, vedere [Compilazione dalla riga di comando con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) per C# e [Compilazione dalla riga di comando ](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) per Visual Basic.  
  
> [!NOTE]
>  Per compilare un assembly in Visual Studio, scegliere **Compila** dal menu **Compila**.  

## <a name="see-also"></a>Vedere anche

 - [Formato dei file di assembly .NET](file-format.md)
 - [Assembly in Common Language Runtime](../../framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 - [Assembly Friend](friend-assemblies.md)  
 - [Procedura: Caricare e scaricare gli assembly (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)  
 - [Procedura: Caricare e scaricare gli assembly (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)  
 - [Procedura: Usare ed eseguire il debug di assembly non caricabili in .NET Core](unloadability-howto.md)
 - [Procedura: Determinare se un file è un assembly (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)  
 - [Procedura: Determinare se un file è un assembly (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)  
