---
title: 'Procedura: Condividere un assembly con altre applicazioni'
description: Vedere come condividere un assembly con altre applicazioni in .NET. Gli assembly possono essere privati (impostazione predefinita) o condivisi. Per condividere un assembly, posizionarlo nella GAC.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 9cef25059968875f17ce5dc77b04c44a2f3945f6
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104656"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a><span data-ttu-id="9daa4-105">Procedura: Condividere un assembly con altre applicazioni</span><span class="sxs-lookup"><span data-stu-id="9daa4-105">How to: Share an assembly with other applications</span></span>
<span data-ttu-id="9daa4-106">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9daa4-106">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  

<span data-ttu-id="9daa4-107">Per condividere un assembly con altre applicazioni, è necessario che venga inserito nella [global assembly cache (GAC)](gac.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-107">In order to share an assembly with other applications, it must be placed in the [global assembly cache (GAC)](gac.md).</span></span>  
  
<span data-ttu-id="9daa4-108">Per condividere un assembly:</span><span class="sxs-lookup"><span data-stu-id="9daa4-108">To share an assembly:</span></span>
  
1. <span data-ttu-id="9daa4-109">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9daa4-109">Create your assembly.</span></span> <span data-ttu-id="9daa4-110">Per altre informazioni, vedere [creare assembly](../../standard/assembly/create.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-110">For more information, see [Create assemblies](../../standard/assembly/create.md).</span></span>  
  
2. <span data-ttu-id="9daa4-111">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="9daa4-111">Assign a strong name to your assembly.</span></span> <span data-ttu-id="9daa4-112">Per altre informazioni, vedere [procedura: firmare un assembly con un nome sicuro](../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-112">For more information, see [How to: Sign an assembly with a strong name](../../standard/assembly/sign-strong-name.md).</span></span>  
  
3. <span data-ttu-id="9daa4-113">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="9daa4-113">Assign version information to your assembly.</span></span> <span data-ttu-id="9daa4-114">Per ulteriori informazioni, vedere [controllo delle versioni degli assembly](../../standard/assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-114">For more information, see [Assembly versioning](../../standard/assembly/versioning.md).</span></span>  
  
4. <span data-ttu-id="9daa4-115">Aggiungere l'assembly al Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="9daa4-115">Add your assembly to the global assembly cache.</span></span> <span data-ttu-id="9daa4-116">Per altre informazioni, vedere [procedura: installare un assembly nel Global assembly cache](install-assembly-into-gac.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-116">For more information, see [How to: Install an assembly into the global assembly cache](install-assembly-into-gac.md).</span></span>  
  
5. <span data-ttu-id="9daa4-117">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="9daa4-117">Access the types contained in the assembly from other applications.</span></span> <span data-ttu-id="9daa4-118">Per altre informazioni, vedere [procedura: fare riferimento a un assembly con nome sicuro](../../standard/assembly/reference-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="9daa4-118">For more information, see [How to: Reference a strong-named assembly](../../standard/assembly/reference-strong-named.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9daa4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9daa4-119">See also</span></span>

- [<span data-ttu-id="9daa4-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="9daa4-120">C# programming guide</span></span>](../../../api/index.md)
- [<span data-ttu-id="9daa4-121">Concetti di programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9daa4-121">Programming concepts (Visual Basic)</span></span>](../../../api/index.md)
- [<span data-ttu-id="9daa4-122">Programmare con gli assembly</span><span class="sxs-lookup"><span data-stu-id="9daa4-122">Program with assemblies</span></span>](../../standard/assembly/index.md)
