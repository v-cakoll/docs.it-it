---
title: 'Procedura: condividere un Assembly con altre applicazioni (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c079250211a4216b09e84140ff537b3f57127967
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="c617c-102">Procedura: condividere un Assembly con altre applicazioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c617c-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="c617c-103">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c617c-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="c617c-104">Per condividerlo con altre applicazioni, un assembly deve essere inserito nella [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="c617c-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="c617c-105">Condivisione di un assembly</span><span class="sxs-lookup"><span data-stu-id="c617c-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="c617c-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="c617c-106">Create your assembly.</span></span> <span data-ttu-id="c617c-107">Per altre informazioni, vedere [Creazione degli assembly](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="c617c-108">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="c617c-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="c617c-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="c617c-110">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="c617c-110">Assign version information to your assembly.</span></span> <span data-ttu-id="c617c-111">Per altre informazioni, vedere [Controllo delle versioni degli assembly](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="c617c-112">Aggiungere l'assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="c617c-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="c617c-113">Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="c617c-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="c617c-114">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c617c-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="c617c-115">Per altre informazioni, vedere [Procedura: Aggiungere un riferimento a un assembly con nome sicuro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="c617c-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c617c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c617c-116">See Also</span></span>  
 <span data-ttu-id="c617c-117">[Concetti relativi alla programmazione](../../../../visual-basic/programming-guide/concepts/index.md) [assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="c617c-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="c617c-118">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="c617c-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
