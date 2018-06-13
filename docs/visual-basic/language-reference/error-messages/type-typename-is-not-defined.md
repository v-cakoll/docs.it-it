---
title: Tipo &#39; &lt;typename&gt; &#39; non è definito
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595186"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="5de9b-102">Tipo &#39; &lt;typename&gt; &#39; non è definito</span><span class="sxs-lookup"><span data-stu-id="5de9b-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="5de9b-103">L'istruzione ha fatto riferimento a un tipo che non è stato definito.</span><span class="sxs-lookup"><span data-stu-id="5de9b-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="5de9b-104">È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum`, `Structure`, `Class`, o `Interface`.</span><span class="sxs-lookup"><span data-stu-id="5de9b-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="5de9b-105">**ID errore:** BC30002</span><span class="sxs-lookup"><span data-stu-id="5de9b-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5de9b-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5de9b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="5de9b-107">Verificare che la definizione del tipo e il relativo riferimento utilizzano la stessa ortografia.</span><span class="sxs-lookup"><span data-stu-id="5de9b-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="5de9b-108">Verificare che la definizione del tipo sia accessibile al riferimento.</span><span class="sxs-lookup"><span data-stu-id="5de9b-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="5de9b-109">Ad esempio, se il tipo in un altro modulo è stato dichiarato `Private`, spostare la definizione del tipo di modulo di riferimento o dichiararla `Public`.</span><span class="sxs-lookup"><span data-stu-id="5de9b-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="5de9b-110">Verificare che lo spazio dei nomi del tipo non viene ridefinito all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="5de9b-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="5de9b-111">In tal caso, utilizzare il `Global` (parola chiave) per qualificare completamente il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="5de9b-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="5de9b-112">Ad esempio, se un progetto definisce uno spazio dei nomi denominato `System`, <xref:System.Object?displayProperty=nameWithType> tipo non è possibile accedere a meno che non è completo, con la `Global` (parola chiave): `Global.System.Object`.</span><span class="sxs-lookup"><span data-stu-id="5de9b-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=nameWithType> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="5de9b-113">Se il tipo è definito, ma la libreria di oggetto o una libreria dei tipi in cui viene definita non è registrata in Visual Basic, fare clic su **Aggiungi riferimento** sul **progetto** menu e quindi selezionare l'oggetto appropriato raccolta o libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="5de9b-113">If the type is defined, but the object library or type library in which it is defined is not registered in Visual Basic, click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="5de9b-114">Verificare che il tipo è un assembly che fa parte del profilo di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5de9b-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="5de9b-115">Per altre informazioni, vedere [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="5de9b-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de9b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5de9b-116">See Also</span></span>  
 [<span data-ttu-id="5de9b-117">Spazi dei nomi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5de9b-117">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [<span data-ttu-id="5de9b-118">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="5de9b-118">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="5de9b-119">Istruzione Structure</span><span class="sxs-lookup"><span data-stu-id="5de9b-119">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="5de9b-120">Istruzione Class</span><span class="sxs-lookup"><span data-stu-id="5de9b-120">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="5de9b-121">Istruzione Interface</span><span class="sxs-lookup"><span data-stu-id="5de9b-121">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="5de9b-122">Gestione dei riferimenti in un progetto</span><span class="sxs-lookup"><span data-stu-id="5de9b-122">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
