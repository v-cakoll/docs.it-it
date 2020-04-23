---
title: 'Procedura: condividere un assembly con altre applicazioni'
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: b4c183c3fc0b04121be8bbc2db4027887cbc3132
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644284"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="9d7f1-102">Procedura: condividere un assembly con altre applicazioni</span><span class="sxs-lookup"><span data-stu-id="9d7f1-102">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="9d7f1-103">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="9d7f1-104">Per condividere un assembly con altre applicazioni, è necessario che venga inserito nella [global assembly cache (GAC)](gac.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-104">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="9d7f1-105">Per condividere un assembly:</span><span class="sxs-lookup"><span data-stu-id="9d7f1-105">To share an assembly:</span></span>
  
1. <span data-ttu-id="9d7f1-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-106">Create your assembly.</span></span> <span data-ttu-id="9d7f1-107">Per altre informazioni, vedere [creare assembly](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-107">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="9d7f1-108">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="9d7f1-109">Per altre informazioni, vedere [procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-109">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="9d7f1-110">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-110">Assign version information to your assembly.</span></span> <span data-ttu-id="9d7f1-111">Per ulteriori informazioni, vedere [controllo delle versioni degli assembly](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-111">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="9d7f1-112">Aggiungere l'assembly al Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-112">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="9d7f1-113">Per altre informazioni, vedere [procedura: installare un assembly nel Global assembly cache](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-113">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="9d7f1-114">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9d7f1-114">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="9d7f1-115">Per altre informazioni, vedere [procedura: fare riferimento a un assembly con nome sicuro](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="9d7f1-115">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d7f1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d7f1-116">See also</span></span>

- [<span data-ttu-id="9d7f1-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9d7f1-117">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="9d7f1-118">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d7f1-118">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="9d7f1-119">Programmare con gli assembly</span><span class="sxs-lookup"><span data-stu-id="9d7f1-119">Program with assemblies</span></span>](../../standard/assembly/index.md)
