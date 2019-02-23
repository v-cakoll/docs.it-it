---
title: 'Procedura: Condividere un Assembly con altre applicazioni (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5388aedc-cb42-4622-8b70-8e701eee057a
ms.openlocfilehash: 1acd665c702dd3b765cdeffde5470893e7097695
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747690"
---
# <a name="how-to-share-an-assembly-with-other-applications-visual-basic"></a><span data-ttu-id="0f718-102">Procedura: Condividere un Assembly con altre applicazioni (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f718-102">How to: Share an Assembly with Other Applications (Visual Basic)</span></span>
<span data-ttu-id="0f718-103">Gli assembly possono essere privati o condivisi. Per impostazione predefinita, i programmi più semplici sono costituiti da un assembly privato perché non sono destinati ad essere usati in altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f718-103">Assemblies can be private or shared: by default, most simple programs consist of a private assembly because they are not intended to be used by other applications.</span></span>  
  
 <span data-ttu-id="0f718-104">Per condividerlo con altre applicazioni, un assembly deve essere inserito nella [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span><span class="sxs-lookup"><span data-stu-id="0f718-104">In order to share an assembly with other applications, it must be placed in the [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).</span></span>  
  
### <a name="sharing-an-assembly"></a><span data-ttu-id="0f718-105">Condivisione di un assembly</span><span class="sxs-lookup"><span data-stu-id="0f718-105">Sharing an assembly</span></span>  
  
1.  <span data-ttu-id="0f718-106">Creare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0f718-106">Create your assembly.</span></span> <span data-ttu-id="0f718-107">Per altre informazioni, vedere [Creazione degli assembly](../../../../framework/app-domains/create-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-107">For more information, see [Creating Assemblies](../../../../framework/app-domains/create-assemblies.md).</span></span>  
  
2.  <span data-ttu-id="0f718-108">Assegnare all'assembly un nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="0f718-108">Assign a strong name to your assembly.</span></span> <span data-ttu-id="0f718-109">Per altre informazioni, vedere [Procedura: Firmare un assembly con un nome sicuro](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
3.  <span data-ttu-id="0f718-110">Assegnare all'assembly le informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="0f718-110">Assign version information to your assembly.</span></span> <span data-ttu-id="0f718-111">Per altre informazioni, vedere [Controllo delle versioni degli assembly](../../../../framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-111">For more information, see [Assembly Versioning](../../../../framework/app-domains/assembly-versioning.md).</span></span>  
  
4.  <span data-ttu-id="0f718-112">Aggiungere l'assembly alla Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="0f718-112">Add your assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="0f718-113">Per altre informazioni, vedere [Procedura: Installare un assembly nella Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-113">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).</span></span>  
  
5.  <span data-ttu-id="0f718-114">Accedere ai tipi contenuti nell'assembly da altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0f718-114">Access the types contained in the assembly from the other applications.</span></span> <span data-ttu-id="0f718-115">Per altre informazioni, vedere [Procedura: Aggiungere un riferimento a un assembly con nome sicuro](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="0f718-115">For more information, see [How to: Reference a Strong-Named Assembly](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f718-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f718-116">See also</span></span>

- [<span data-ttu-id="0f718-117">Nozioni di base sulla programmazione</span><span class="sxs-lookup"><span data-stu-id="0f718-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="0f718-118">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="0f718-118">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="0f718-119">Programmazione con gli assembly</span><span class="sxs-lookup"><span data-stu-id="0f718-119">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
