---
title: /Imports (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: 15
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
ms.openlocfilehash: e994e94dcc3cd00f868b6ae90e4c019eb5b9e2eb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="imports-visual-basic"></a><span data-ttu-id="3ec89-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ec89-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="3ec89-103">Importa gli spazi dei nomi da un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="3ec89-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ec89-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="3ec89-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3ec89-105">Arguments</span></span>  
  
|<span data-ttu-id="3ec89-106">Termine</span><span class="sxs-lookup"><span data-stu-id="3ec89-106">Term</span></span>|<span data-ttu-id="3ec89-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="3ec89-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="3ec89-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="3ec89-108">Required.</span></span> <span data-ttu-id="3ec89-109">Elenco delimitato da virgole degli spazi dei nomi da importare.</span><span class="sxs-lookup"><span data-stu-id="3ec89-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ec89-110">Note</span><span class="sxs-lookup"><span data-stu-id="3ec89-110">Remarks</span></span>  
 <span data-ttu-id="3ec89-111">Il `/imports` opzione consente di importare qualsiasi spazio dei nomi definito all'interno del gruppo di file di origine o da qualsiasi assembly di riferimento correnti.</span><span class="sxs-lookup"><span data-stu-id="3ec89-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="3ec89-112">I membri di uno spazio dei nomi specificati con `/imports` sono disponibili a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="3ec89-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="3ec89-113">Utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per usare uno spazio dei nomi in un file di codice sorgente singolo.</span><span class="sxs-lookup"><span data-stu-id="3ec89-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="3ec89-114">Per impostare /Imports nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3ec89-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="3ec89-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="3ec89-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="3ec89-116">Nel **Project** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="3ec89-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="3ec89-117">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="3ec89-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="3ec89-118">2.  Fare clic su di **riferimenti** scheda.</span><span class="sxs-lookup"><span data-stu-id="3ec89-118">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="3ec89-119">3.  Immettere il nome dello spazio dei nomi nella casella accanto il **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="3ec89-119">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="3ec89-120">4.  Fare clic su di **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="3ec89-120">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ec89-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ec89-121">Example</span></span>  
 <span data-ttu-id="3ec89-122">Il codice seguente viene compilato quando `/imports:system` è specificato.</span><span class="sxs-lookup"><span data-stu-id="3ec89-122">The following code compiles when `/imports:system` is specified.</span></span>  
  
 <span data-ttu-id="3ec89-123">[!code-vb[VbVbalrCompiler numero&21;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ec89-123">[!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec89-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ec89-124">See Also</span></span>  
 <span data-ttu-id="3ec89-125">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ec89-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="3ec89-126"> [I riferimenti e istruzione Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3ec89-126"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="3ec89-127"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="3ec89-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
