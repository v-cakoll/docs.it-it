---
title: /imports (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a><span data-ttu-id="c4b6f-102">/imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4b6f-102">/imports (Visual Basic)</span></span>
<span data-ttu-id="c4b6f-103">Importa gli spazi dei nomi da un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b6f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c4b6f-104">Syntax</span></span>  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4b6f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="c4b6f-105">Arguments</span></span>  
  
|<span data-ttu-id="c4b6f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="c4b6f-106">Term</span></span>|<span data-ttu-id="c4b6f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="c4b6f-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="c4b6f-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-108">Required.</span></span> <span data-ttu-id="c4b6f-109">Elenco delimitato da virgole degli spazi dei nomi da importare.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4b6f-110">Note</span><span class="sxs-lookup"><span data-stu-id="c4b6f-110">Remarks</span></span>  
 <span data-ttu-id="c4b6f-111">Il `/imports` opzione consente di importare qualsiasi spazio dei nomi definito all'interno del gruppo di file di origine o da qualsiasi assembly di riferimento correnti.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-111">The `/imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="c4b6f-112">I membri di uno spazio dei nomi specificati con `/imports` sono disponibili a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-112">The members in a namespace specified with `/imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="c4b6f-113">Utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per utilizzare uno spazio dei nomi in un file di codice sorgente singolo.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="c4b6f-114">Per impostare /Imports nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c4b6f-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c4b6f-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c4b6f-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c4b6f-117">2.  Fare clic sulla scheda **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="c4b6f-118">3.  Immettere il nome dello spazio dei nomi nella casella accanto il **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="c4b6f-119">4.  Fare clic su di **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4b6f-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="c4b6f-120">Example</span></span>  
 <span data-ttu-id="c4b6f-121">Il codice seguente viene compilato quando `/imports:system` è specificato.</span><span class="sxs-lookup"><span data-stu-id="c4b6f-121">The following code compiles when `/imports:system` is specified.</span></span>  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c4b6f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c4b6f-122">See Also</span></span>  
 [<span data-ttu-id="c4b6f-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4b6f-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c4b6f-124">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="c4b6f-124">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="c4b6f-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="c4b6f-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
