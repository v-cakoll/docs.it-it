---
title: 'Procedura: condividere un Assembly con altre applicazioni (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
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
ms.openlocfilehash: ceebb3934c269284db18c9ca8e561417eaf5baa1
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="8c8be-102">Procedura: condividere un Assembly con altre applicazioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c8be-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="8c8be-103">Gli assembly possono essere privati o condivisi: per impostazione predefinita, la maggior parte dei programmi semplici sono composti da un assembly privato perché non sono progettati per essere utilizzato da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8c8be-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="8c8be-104">Per condividere un assembly con altre applicazioni, deve essere inserito nel [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span><span class="sxs-lookup"><span data-stu-id="8c8be-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](http://msdn.microsoft.com/library/cf5eacd0-d3ec-4879-b6da-5fd5e4372202) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="8c8be-105">Condivisione di un assembly</span><span class="sxs-lookup"><span data-stu-id="8c8be-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="8c8be-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8c8be-106">Create your assembly.</span></span> <span data-ttu-id="8c8be-107">Per ulteriori informazioni, vedere [creazione di assembly](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span><span class="sxs-lookup"><span data-stu-id="8c8be-107">For more information, see [Creating Assemblies](http://msdn.microsoft.com/library/54832ee9-dca8-4c8b-913c-c0b9d265e9a4).</span></span>  
  
2.  <span data-ttu-id="8c8be-108">Assegnare un nome sicuro all'assembly.</span><span class="sxs-lookup"><span data-stu-id="8c8be-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="8c8be-109">Per ulteriori informazioni, vedere [procedura: firmare un Assembly con un nome sicuro](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span><span class="sxs-lookup"><span data-stu-id="8c8be-109">For more information, see [How to: Sign an Assembly with a Strong Name](http://msdn.microsoft.com/library/2c30799a-a826-46b4-a25d-c584027a6c67).</span></span>  
  
3.  <span data-ttu-id="8c8be-110">Assegnare le informazioni sulla versione per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="8c8be-110">Assign version information to your assembly.</span></span> <span data-ttu-id="8c8be-111">Per ulteriori informazioni, vedere [il controllo delle versioni di Assembly](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="8c8be-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="8c8be-112">Aggiungere l'assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="8c8be-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="8c8be-113">Per ulteriori informazioni, vedere [procedura: installare un Assembly nella Global Assembly Cache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span><span class="sxs-lookup"><span data-stu-id="8c8be-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](http://msdn.microsoft.com/library/a7e6f091-d02c-49ba-b736-7295cb0eb743).</span></span>  
  
5.  <span data-ttu-id="8c8be-114">Accedere ai tipi contenuti nell'assembly dalle altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8c8be-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="8c8be-115">Per ulteriori informazioni, vedere [procedura: fare riferimento a un Assembly con nomi sicuri](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="8c8be-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c8be-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c8be-116">See Also</span></span>  
 <span data-ttu-id="8c8be-117">[Concetti relativi alla programmazione](../../../../visual-basic/programming-guide/concepts/index.md)
 [assembly e Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="8c8be-117">[Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)
 [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="8c8be-118"> [Programmazione con assembly](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span><span class="sxs-lookup"><span data-stu-id="8c8be-118"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6)</span></span>
