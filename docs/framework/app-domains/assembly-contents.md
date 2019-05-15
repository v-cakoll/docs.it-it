---
title: Contenuto degli assembly
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd41051bd770d3579137aa158e70cef41aed49f8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607833"
---
# <a name="assembly-contents"></a><span data-ttu-id="3fcec-102">Contenuto degli assembly</span><span class="sxs-lookup"><span data-stu-id="3fcec-102">Assembly Contents</span></span>
<span data-ttu-id="3fcec-103">Per grandi linee, un assembly statico è costituito da quattro elementi:</span><span class="sxs-lookup"><span data-stu-id="3fcec-103">In general, a static assembly can consist of four elements:</span></span>  
  
- <span data-ttu-id="3fcec-104">Il [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md) che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="3fcec-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
- <span data-ttu-id="3fcec-105">I metadati dei tipi.</span><span class="sxs-lookup"><span data-stu-id="3fcec-105">Type metadata.</span></span>  
  
- <span data-ttu-id="3fcec-106">Il codice Microsoft Intermediate Language (MSIL) che implementa i tipi.</span><span class="sxs-lookup"><span data-stu-id="3fcec-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
- <span data-ttu-id="3fcec-107">Un insieme di risorse.</span><span class="sxs-lookup"><span data-stu-id="3fcec-107">A set of resources.</span></span>  
  
 <span data-ttu-id="3fcec-108">Il manifesto dell'assembly è il solo elemento obbligatorio, ma il corretto funzionamento dell'assembly dipende anche dalla presenza di tipi o risorse.</span><span class="sxs-lookup"><span data-stu-id="3fcec-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="3fcec-109">Tali elementi possono essere raggruppati in un assembly in più modi.</span><span class="sxs-lookup"><span data-stu-id="3fcec-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="3fcec-110">È possibile raggruppare tutti gli elementi in un unico file fisico, come illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="3fcec-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 ![Diagramma che illustra un assembly a file singolo denominato MyAssembly.dll.](./media/assembly-contents/single-file-assembly.gif)  
  
 <span data-ttu-id="3fcec-112">In alternativa, è possibile distribuire gli elementi di un assembly in più file.</span><span class="sxs-lookup"><span data-stu-id="3fcec-112">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="3fcec-113">Questi file possono essere moduli di codice compilato (con estensione netmodule), risorse (ad esempio file con estensione jpg o bmp) o altri file richiesti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3fcec-113">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="3fcec-114">Si opta per un assembly su più file quando si desidera combinare moduli scritti in diversi linguaggi e ottimizzare il download di un'applicazione inserendo i tipi utilizzati più raramente in un modulo che verrà scaricato solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="3fcec-114">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="3fcec-115">Nella figura riportata di seguito lo sviluppatore di un'ipotetica applicazione ha scelto di inserire il codice di alcune utilità in un modulo diverso e di includere un file di risorse di grandi dimensioni (in questo caso si tratta di un'immagine BMP) nel file originale.</span><span class="sxs-lookup"><span data-stu-id="3fcec-115">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="3fcec-116">L'ambiente .NET Framework provvede al download di un file solo quando vi si fa riferimento. Tenere in un file separato dall'applicazione il codice a cui si fa riferimento più raramente consente di ottimizzare il download del codice.</span><span class="sxs-lookup"><span data-stu-id="3fcec-116">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 ![Diagramma che illustra un assembly con più file.](./media/assembly-contents/multifile-assembly-diagram.gif) 
  
> [!NOTE]
>  <span data-ttu-id="3fcec-118">I file che compongono un assembly su più file non vengono inclusi nel collegamento fisico operato dal file system.</span><span class="sxs-lookup"><span data-stu-id="3fcec-118">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="3fcec-119">Essi vengono invece collegati tramite il manifesto dell'assembly e Common Language Runtime li gestisce come un unico componente.</span><span class="sxs-lookup"><span data-stu-id="3fcec-119">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="3fcec-120">Nella figura riportata di seguito tutti e tre i file appartengono a un assembly, come descritto nel manifesto dell'assembly contenuto in MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="3fcec-120">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="3fcec-121">Tali file vengono gestiti dal file system come tre file distinti.</span><span class="sxs-lookup"><span data-stu-id="3fcec-121">To the file system, they are three separate files.</span></span> <span data-ttu-id="3fcec-122">Si noti che il file Util.netmodule è stato compilato come modulo perché in esso non sono contenute informazioni sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="3fcec-122">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="3fcec-123">Quando è stato creato l'assembly, il relativo manifesto è stato aggiunto a MyAssembly.dll, indicandone la relazione con Util.netmodule e Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="3fcec-123">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="3fcec-124">Oggi nella progettazione del codice sorgente si prendono decisioni esplicite su come partizionare le funzionalità della propria applicazione in uno o più file.</span><span class="sxs-lookup"><span data-stu-id="3fcec-124">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="3fcec-125">Nel progettare codice .NET Framework, si prenderanno decisioni simili riguardo a come partizionare le funzionalità in uno o più assembly.</span><span class="sxs-lookup"><span data-stu-id="3fcec-125">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fcec-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fcec-126">See also</span></span>

- [<span data-ttu-id="3fcec-127">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="3fcec-127">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [<span data-ttu-id="3fcec-128">Manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="3fcec-128">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)
- [<span data-ttu-id="3fcec-129">Considerazioni sulla sicurezza degli assembly</span><span class="sxs-lookup"><span data-stu-id="3fcec-129">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
