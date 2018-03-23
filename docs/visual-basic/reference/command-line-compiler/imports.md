---
title: -imports (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d81e9d2bd55e6e38e337805b950a0b85680d129b
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="95a02-102">-imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95a02-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="95a02-103">Importa gli spazi dei nomi da un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="95a02-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95a02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95a02-104">Syntax</span></span>  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="95a02-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="95a02-105">Arguments</span></span>  
  
|<span data-ttu-id="95a02-106">Termine</span><span class="sxs-lookup"><span data-stu-id="95a02-106">Term</span></span>|<span data-ttu-id="95a02-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="95a02-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="95a02-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="95a02-108">Required.</span></span> <span data-ttu-id="95a02-109">Elenco delimitato da virgole degli spazi dei nomi da importare.</span><span class="sxs-lookup"><span data-stu-id="95a02-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95a02-110">Note</span><span class="sxs-lookup"><span data-stu-id="95a02-110">Remarks</span></span>  
 <span data-ttu-id="95a02-111">Il `-imports` opzione consente di importare qualsiasi spazio dei nomi definito all'interno del gruppo di file di origine o da qualsiasi assembly di riferimento correnti.</span><span class="sxs-lookup"><span data-stu-id="95a02-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="95a02-112">I membri di uno spazio dei nomi specificati con `-imports` sono disponibili a tutti i file di codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="95a02-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="95a02-113">Utilizzare il [istruzione Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per utilizzare uno spazio dei nomi in un file di codice sorgente singolo.</span><span class="sxs-lookup"><span data-stu-id="95a02-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="95a02-114">Per impostare /Imports nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="95a02-114">To set /imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="95a02-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="95a02-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="95a02-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="95a02-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="95a02-117">2.  Fare clic sulla scheda **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="95a02-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="95a02-118">3.  Immettere il nome dello spazio dei nomi nella casella accanto il **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="95a02-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="95a02-119">4.  Fare clic su di **Aggiungi importazione utente** pulsante.</span><span class="sxs-lookup"><span data-stu-id="95a02-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="95a02-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="95a02-120">Example</span></span>  
 <span data-ttu-id="95a02-121">Il codice seguente viene compilato quando `/imports:system.globalization` è specificato.</span><span class="sxs-lookup"><span data-stu-id="95a02-121">The following code compiles when `/imports:system.globalization` is specified.</span></span> <span data-ttu-id="95a02-122">Senza di esso, compilazione corretta richiede che un `Imports System.Globalization` istruzione essere contenuto all'inizio del file del codice sorgente o che la proprietà essere qualificato come `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="95a02-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span> 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="95a02-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95a02-123">See Also</span></span>  
 [<span data-ttu-id="95a02-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95a02-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="95a02-125">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="95a02-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="95a02-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="95a02-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
