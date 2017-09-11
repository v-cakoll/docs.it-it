---
title: 'Procedura: Condividere un assembly con altre applicazioni (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 85117cfdc9b12a93891e89727412a03acc83289b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a><span data-ttu-id="db4fd-102">Procedura: Condividere un assembly con altre applicazioni (C#)</span><span class="sxs-lookup"><span data-stu-id="db4fd-102">How to: Share an Assembly with Other Applications (C#)</span></span>
<span data-ttu-id="db4fd-103">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="db4fd-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="db4fd-104">Per condividerlo con altre applicazioni, un assembly deve essere inserito nella [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="db4fd-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="db4fd-105">Condivisione di un assembly</span><span class="sxs-lookup"><span data-stu-id="db4fd-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="db4fd-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="db4fd-106">Create your assembly.</span></span> <span data-ttu-id="db4fd-107">Per altre informazioni, vedere [Creazione degli assembly](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="db4fd-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="db4fd-108">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="db4fd-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="db4fd-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="db4fd-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="db4fd-110">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="db4fd-110">Assign version information to your assembly.</span></span> <span data-ttu-id="db4fd-111">Per altre informazioni, vedere [Controllo delle versioni degli assembly](https://msdn.microsoft.com/library/51ket42z).</span><span class="sxs-lookup"><span data-stu-id="db4fd-111">For more information, see [Assembly Versioning](https://msdn.microsoft.com/library/51ket42z).</span></span>  
  
4.  <span data-ttu-id="db4fd-112">Aggiungere l'assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="db4fd-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="db4fd-113">Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="db4fd-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="db4fd-114">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="db4fd-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="db4fd-115">Per altre informazioni, vedere [Procedura: Aggiungere un riferimento a un assembly con nome sicuro](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span><span class="sxs-lookup"><span data-stu-id="db4fd-115">For more information, see [How to: Reference a Strong-Named Assembly](http://msdn.microsoft.com/library/4c6a406a-b5eb-44fa-b4ed-4e95bb95a813).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db4fd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db4fd-116">See Also</span></span>  
 <span data-ttu-id="db4fd-117">[Guida per programmatori C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="db4fd-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="db4fd-118">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="db4fd-118">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)

