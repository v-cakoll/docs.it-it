---
title: "Tipo &quot;&lt;typename&gt;&quot; non è definito | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 55b76e9d080a2e2e9fe6e9737a713524ea6409f6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="669ee-102">Tipo '&lt;typename&gt;' non è definito</span><span class="sxs-lookup"><span data-stu-id="669ee-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="669ee-103">L'istruzione ha fatto riferimento a un tipo che non è stato definito.</span><span class="sxs-lookup"><span data-stu-id="669ee-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="669ee-104">È possibile definire un tipo in un'istruzione di dichiarazione, ad esempio `Enum`, `Structure`, `Class`, o `Interface`.</span><span class="sxs-lookup"><span data-stu-id="669ee-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="669ee-105">**ID errore:** BC30002</span><span class="sxs-lookup"><span data-stu-id="669ee-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="669ee-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="669ee-106">To correct this error</span></span>  
  
-   <span data-ttu-id="669ee-107">Assicurarsi che la definizione del tipo e il relativo riferimento utilizzano la stessa ortografia.</span><span class="sxs-lookup"><span data-stu-id="669ee-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="669ee-108">Assicurarsi che la definizione del tipo sia accessibile al riferimento.</span><span class="sxs-lookup"><span data-stu-id="669ee-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="669ee-109">Ad esempio, se il tipo è un altro modulo ed è stato dichiarato `Private`, spostare la definizione del tipo di modulo di riferimento o dichiararla `Public`.</span><span class="sxs-lookup"><span data-stu-id="669ee-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="669ee-110">Verificare che lo spazio dei nomi del tipo non sia ridefinito all'interno del progetto.</span><span class="sxs-lookup"><span data-stu-id="669ee-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="669ee-111">In tal caso, utilizzare il `Global` parola chiave per il nome tipo completo.</span><span class="sxs-lookup"><span data-stu-id="669ee-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="669ee-112">Ad esempio, se un progetto definisce uno spazio dei nomi denominato `System`, <xref:System.Object?displayProperty=fullName>tipo non è possibile accedere a meno che non è completo, con la `Global` (parola chiave): `Global.System.Object`.</xref:System.Object?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="669ee-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=fullName> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="669ee-113">Se il tipo è definito, ma non è registrata la libreria di oggetto o una libreria dei tipi in cui è definito [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], fare clic su **Aggiungi riferimento** sul **progetto** dal menu e quindi selezionare la libreria di oggetto appropriato o una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="669ee-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="669ee-114">Verificare che il tipo in un assembly che fa parte del profilo di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="669ee-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="669ee-115">Per ulteriori informazioni, vedere [risoluzione dei problemi di destinazione .NET Framework](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span><span class="sxs-lookup"><span data-stu-id="669ee-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="669ee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="669ee-116">See Also</span></span>  
 <span data-ttu-id="669ee-117">[Spazi dei nomi in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="669ee-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="669ee-118"> [Istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="669ee-118"> [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="669ee-119"> [Istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="669ee-119"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="669ee-120"> [Istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md) </span><span class="sxs-lookup"><span data-stu-id="669ee-120"> [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) </span></span>  
<span data-ttu-id="669ee-121"> [Istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="669ee-121"> [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="669ee-122"> [Gestione dei riferimenti in un progetto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span><span class="sxs-lookup"><span data-stu-id="669ee-122"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span></span>
