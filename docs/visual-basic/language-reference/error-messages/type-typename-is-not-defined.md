---
title: Tipo '<typename>' non definito
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: c2675d61307d92da1710368668f43af3559060a3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825040"
---
# <a name="type-typename-is-not-defined"></a><span data-ttu-id="78fe4-102">Tipo '\<nomeTipo >' non è definito</span><span class="sxs-lookup"><span data-stu-id="78fe4-102">Type '\<typename>' is not defined</span></span>
<span data-ttu-id="78fe4-103">L'istruzione ha fatto riferimento a un tipo che non è stato definito.</span><span class="sxs-lookup"><span data-stu-id="78fe4-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="78fe4-104">È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum`, `Structure`, `Class`, o `Interface`.</span><span class="sxs-lookup"><span data-stu-id="78fe4-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="78fe4-105">**ID errore:** BC30002</span><span class="sxs-lookup"><span data-stu-id="78fe4-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78fe4-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="78fe4-106">To correct this error</span></span>  
  
-   <span data-ttu-id="78fe4-107">Assicurarsi che la definizione del tipo e il relativo riferimento usino entrambi la stessa ortografia.</span><span class="sxs-lookup"><span data-stu-id="78fe4-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="78fe4-108">Verificare che la definizione del tipo sia accessibile al riferimento.</span><span class="sxs-lookup"><span data-stu-id="78fe4-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="78fe4-109">Ad esempio, se il tipo è in un altro modulo ed è stato dichiarato `Private`spostare la definizione del tipo per il riferimento modulo o dichiararla `Public`.</span><span class="sxs-lookup"><span data-stu-id="78fe4-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="78fe4-110">Assicurarsi che lo spazio dei nomi del tipo viene ridefinito non all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="78fe4-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="78fe4-111">Se si tratta, usare il `Global` parola chiave per qualificare completamente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="78fe4-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="78fe4-112">Ad esempio, se un progetto definisce uno spazio dei nomi denominato `System`, il <xref:System.Object?displayProperty=nameWithType> tipo non è accessibile, a meno che non è completo, con la `Global` parola chiave: `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="78fe4-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="78fe4-113">Se il tipo è definito, ma la libreria di oggetto o una libreria dei tipi in cui viene definito non è registrata in Visual Basic, scegliere **Aggiungi riferimento** nel **progetto** menu e quindi selezionare l'oggetto sia appropriato raccolta o libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="78fe4-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="78fe4-114">Assicurarsi che il tipo è in un assembly che fa parte del profilo di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="78fe4-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="78fe4-115">Per altre informazioni, vedere [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="78fe4-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78fe4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78fe4-116">See also</span></span>

- [<span data-ttu-id="78fe4-117">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78fe4-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="78fe4-118">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="78fe4-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="78fe4-119">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="78fe4-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)
- [<span data-ttu-id="78fe4-120">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="78fe4-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="78fe4-121">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="78fe4-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="78fe4-122">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="78fe4-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
