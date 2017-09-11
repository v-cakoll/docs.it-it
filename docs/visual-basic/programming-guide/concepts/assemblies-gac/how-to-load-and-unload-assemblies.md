---
title: 'Procedura: caricare e scaricare gli assembly (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: bbc84236-04b6-4c1b-9672-52773f65a5dc
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e38be72bb58573b532fa42a569563df0be8301d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-load-and-unload-assemblies-visual-basic"></a><span data-ttu-id="64a2b-102">Procedura: caricare e scaricare gli assembly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64a2b-102">How to: Load and Unload Assemblies (Visual Basic)</span></span>
<span data-ttu-id="64a2b-103">Gli assembly a cui fa riferimento il programma automaticamente verrà caricati in fase di compilazione, ma è anche possibile caricare assembly specifici nel dominio applicazione corrente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="64a2b-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="64a2b-104">Per ulteriori informazioni, vedere [procedura: caricamento di assembly in un dominio applicazione](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="64a2b-104">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
 <span data-ttu-id="64a2b-105">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="64a2b-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="64a2b-106">Anche se l'assembly esce dall'ambito, il file effettivo dell'assembly rimane caricato finché non vengono scaricati tutti i domini applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="64a2b-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="64a2b-107">Se si desidera scaricare alcuni assembly ma non altri, è consigliabile creare un nuovo dominio applicazione, l'esecuzione del codice all'interno del dominio e quindi scaricare tale dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="64a2b-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="64a2b-108">Per ulteriori informazioni, vedere [procedura: scaricare un dominio applicazione](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="64a2b-108">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="64a2b-109">Per caricare un assembly in un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="64a2b-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="64a2b-110">Utilizzare uno dei numerosi metodi di caricamento di classi <xref:System.AppDomain>e <xref:System.Reflection>.</xref:System.Reflection> </xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="64a2b-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="64a2b-111">Per ulteriori informazioni, vedere [procedura: caricamento di assembly in un dominio applicazione](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span><span class="sxs-lookup"><span data-stu-id="64a2b-111">For more information, see [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="64a2b-112">Per scaricare un dominio applicazione</span><span class="sxs-lookup"><span data-stu-id="64a2b-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="64a2b-113">Non è possibile scaricare un singolo assembly senza scaricare tutti i domini applicazione che lo contengono.</span><span class="sxs-lookup"><span data-stu-id="64a2b-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="64a2b-114">Utilizzare il `Unload` metodo <xref:System.AppDomain>per scaricare i domini applicazione.</xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="64a2b-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="64a2b-115">Per ulteriori informazioni, vedere [procedura: scaricare un dominio applicazione](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span><span class="sxs-lookup"><span data-stu-id="64a2b-115">For more information, see [How to: Unload an Application Domain](http://msdn.microsoft.com/library/f356116d-e415-4f7c-a332-6e6a60227192).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a2b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64a2b-116">See Also</span></span>  
 <span data-ttu-id="64a2b-117">[Concetti di programmazione](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="64a2b-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="64a2b-118"> [Gli assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="64a2b-118"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="64a2b-119"> [Procedura: caricare assembly nel dominio applicazione](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span><span class="sxs-lookup"><span data-stu-id="64a2b-119"> [How to: Load Assemblies into an Application Domain](http://msdn.microsoft.com/library/1432aa2d-bd83-4346-bf3b-a1b7920e2aa9)</span></span>
