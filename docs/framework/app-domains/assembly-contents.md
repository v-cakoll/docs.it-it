---
title: Contenuto degli assembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- assemblies [.NET Framework], single-file
- single-file assemblies
- multifile assemblies
ms.assetid: 28116714-da77-45f7-826d-fa035d121948
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b51380126de164a4e0934068c7e0de55f5f3d92e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-contents"></a><span data-ttu-id="48884-102">Contenuto degli assembly</span><span class="sxs-lookup"><span data-stu-id="48884-102">Assembly Contents</span></span>
<span data-ttu-id="48884-103">Per grandi linee, un assembly statico è costituito da quattro elementi:</span><span class="sxs-lookup"><span data-stu-id="48884-103">In general, a static assembly can consist of four elements:</span></span>  
  
-   <span data-ttu-id="48884-104">Il [manifesto dell'assembly](../../../docs/framework/app-domains/assembly-manifest.md) che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="48884-104">The [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md), which contains assembly metadata.</span></span>  
  
-   <span data-ttu-id="48884-105">I metadati dei tipi.</span><span class="sxs-lookup"><span data-stu-id="48884-105">Type metadata.</span></span>  
  
-   <span data-ttu-id="48884-106">Il codice Microsoft Intermediate Language (MSIL) che implementa i tipi.</span><span class="sxs-lookup"><span data-stu-id="48884-106">Microsoft intermediate language (MSIL) code that implements the types.</span></span>  
  
-   <span data-ttu-id="48884-107">Un insieme di risorse.</span><span class="sxs-lookup"><span data-stu-id="48884-107">A set of resources.</span></span>  
  
 <span data-ttu-id="48884-108">Il manifesto dell'assembly è il solo elemento obbligatorio, ma il corretto funzionamento dell'assembly dipende anche dalla presenza di tipi o risorse.</span><span class="sxs-lookup"><span data-stu-id="48884-108">Only the assembly manifest is required, but either types or resources are needed to give the assembly any meaningful functionality.</span></span>  
  
 <span data-ttu-id="48884-109">Tali elementi possono essere raggruppati in un assembly in più modi.</span><span class="sxs-lookup"><span data-stu-id="48884-109">There are several ways to group these elements in an assembly.</span></span> <span data-ttu-id="48884-110">È possibile raggruppare tutti gli elementi in un unico file fisico, come illustrato nella figura che segue.</span><span class="sxs-lookup"><span data-stu-id="48884-110">You can group all elements in a single physical file, which is shown in the following illustration.</span></span>  
  
 <span data-ttu-id="48884-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span><span class="sxs-lookup"><span data-stu-id="48884-111">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover1.gif "assemblyover1")</span></span>  
<span data-ttu-id="48884-112">Assembly a file singolo</span><span class="sxs-lookup"><span data-stu-id="48884-112">Single-file assembly</span></span>  
  
 <span data-ttu-id="48884-113">In alternativa, è possibile distribuire gli elementi di un assembly in più file.</span><span class="sxs-lookup"><span data-stu-id="48884-113">Alternatively, the elements of an assembly can be contained in several files.</span></span> <span data-ttu-id="48884-114">Questi file possono essere moduli di codice compilato (con estensione netmodule), risorse (ad esempio file con estensione jpg o bmp) o altri file richiesti dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="48884-114">These files can be modules of compiled code (.netmodule), resources (such as .bmp or .jpg files), or other files required by the application.</span></span> <span data-ttu-id="48884-115">Si opta per un assembly su più file quando si desidera combinare moduli scritti in diversi linguaggi e ottimizzare il download di un'applicazione inserendo i tipi utilizzati più raramente in un modulo che verrà scaricato solo se necessario.</span><span class="sxs-lookup"><span data-stu-id="48884-115">Create a multifile assembly when you want to combine modules written in different languages and to optimize downloading an application by putting seldom used types in a module that is downloaded only when needed.</span></span>  
  
 <span data-ttu-id="48884-116">Nella figura riportata di seguito lo sviluppatore di un'ipotetica applicazione ha scelto di inserire il codice di alcune utilità in un modulo diverso e di includere un file di risorse di grandi dimensioni (in questo caso si tratta di un'immagine BMP) nel file originale.</span><span class="sxs-lookup"><span data-stu-id="48884-116">In the following illustration, the developer of a hypothetical application has chosen to separate some utility code into a different module and to keep a large resource file (in this case a .bmp image) in its original file.</span></span> <span data-ttu-id="48884-117">L'ambiente .NET Framework provvede al download di un file solo quando vi si fa riferimento. Tenere in un file separato dall'applicazione il codice a cui si fa riferimento più raramente consente di ottimizzare il download del codice.</span><span class="sxs-lookup"><span data-stu-id="48884-117">The .NET Framework downloads a file only when it is referenced; keeping infrequently referenced code in a separate file from the application optimizes code download.</span></span>  
  
 <span data-ttu-id="48884-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span><span class="sxs-lookup"><span data-stu-id="48884-118">![MyAssembly.dll](../../../docs/framework/app-domains/media/assemblyover2.gif "assemblyover2")</span></span>  
<span data-ttu-id="48884-119">Assembly su più file</span><span class="sxs-lookup"><span data-stu-id="48884-119">Multifile assembly</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48884-120">I file che compongono un assembly su più file non vengono inclusi nel collegamento fisico operato dal file system.</span><span class="sxs-lookup"><span data-stu-id="48884-120">The files that make up a multifile assembly are not physically linked by the file system.</span></span> <span data-ttu-id="48884-121">Essi vengono invece collegati tramite il manifesto dell'assembly e Common Language Runtime li gestisce come un unico componente.</span><span class="sxs-lookup"><span data-stu-id="48884-121">Rather, they are linked through the assembly manifest and the common language runtime manages them as a unit.</span></span>  
  
 <span data-ttu-id="48884-122">Nella figura riportata di seguito tutti e tre i file appartengono a un assembly, come descritto nel manifesto dell'assembly contenuto in MyAssembly.dll.</span><span class="sxs-lookup"><span data-stu-id="48884-122">In this illustration, all three files belong to an assembly, as described in the assembly manifest contained in MyAssembly.dll.</span></span> <span data-ttu-id="48884-123">Tali file vengono gestiti dal file system come tre file distinti.</span><span class="sxs-lookup"><span data-stu-id="48884-123">To the file system, they are three separate files.</span></span> <span data-ttu-id="48884-124">Si noti che il file Util.netmodule è stato compilato come modulo perché in esso non sono contenute informazioni sull'assembly.</span><span class="sxs-lookup"><span data-stu-id="48884-124">Note that the file Util.netmodule was compiled as a module because it contains no assembly information.</span></span> <span data-ttu-id="48884-125">Quando è stato creato l'assembly, il relativo manifesto è stato aggiunto a MyAssembly.dll, indicandone la relazione con Util.netmodule e Graphic.bmp.</span><span class="sxs-lookup"><span data-stu-id="48884-125">When the assembly was created, the assembly manifest was added to MyAssembly.dll, indicating its relationship with Util.netmodule and Graphic.bmp.</span></span>  
  
 <span data-ttu-id="48884-126">Oggi nella progettazione del codice sorgente si prendono decisioni esplicite su come partizionare le funzionalità della propria applicazione in uno o più file.</span><span class="sxs-lookup"><span data-stu-id="48884-126">As you currently design your source code, you make explicit decisions about how to partition the functionality of your application into one or more files.</span></span> <span data-ttu-id="48884-127">Nel progettare codice .NET Framework, si prenderanno decisioni simili riguardo a come partizionare le funzionalità in uno o più assembly.</span><span class="sxs-lookup"><span data-stu-id="48884-127">When designing .NET Framework code, you will make similar decisions about how to partition the functionality into one or more assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48884-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48884-128">See Also</span></span>  
 [<span data-ttu-id="48884-129">Assembly in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="48884-129">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="48884-130">Manifesto dell'assembly</span><span class="sxs-lookup"><span data-stu-id="48884-130">Assembly Manifest</span></span>](../../../docs/framework/app-domains/assembly-manifest.md)  
 [<span data-ttu-id="48884-131">Considerazioni sulla sicurezza degli assembly</span><span class="sxs-lookup"><span data-stu-id="48884-131">Assembly Security Considerations</span></span>](../../../docs/framework/app-domains/assembly-security-considerations.md)
