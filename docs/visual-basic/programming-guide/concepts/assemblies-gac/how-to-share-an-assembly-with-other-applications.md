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
ms.openlocfilehash: 0ad7a3f2ee82d0a582e755035448d565a9a8cb9d
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="3b569-102">Procedura: condividere un Assembly con altre applicazioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b569-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="3b569-103">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b569-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="3b569-104">Per condividerlo con altre applicazioni, un assembly deve essere inserito nella [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="3b569-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="3b569-105">Condivisione di un assembly</span><span class="sxs-lookup"><span data-stu-id="3b569-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="3b569-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3b569-106">Create your assembly.</span></span> <span data-ttu-id="3b569-107">Per altre informazioni, vedere [Creazione degli assembly](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="3b569-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="3b569-108">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="3b569-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="3b569-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="3b569-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="3b569-110">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="3b569-110">Assign version information to your assembly.</span></span> <span data-ttu-id="3b569-111">Per altre informazioni, vedere [Controllo delle versioni degli assembly](../../../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="3b569-111">For more information, see [Assembly Versioning](../../../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="3b569-112">Aggiungere l'assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="3b569-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="3b569-113">Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="3b569-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="3b569-114">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="3b569-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="3b569-115">Per altre informazioni, vedere [Procedura: Aggiungere un riferimento a un assembly con nome sicuro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="3b569-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b569-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b569-116">See Also</span></span>  
 <span data-ttu-id="3b569-117">[Concetti relativi alla programmazione](../../../../visual-basic/programming-guide/concepts/index.md) [assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="3b569-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>  
 [<span data-ttu-id="3b569-118">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="3b569-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
