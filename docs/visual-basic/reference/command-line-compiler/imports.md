---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 2a1dd19189ff65413255b9bc137e1a7f0227bbe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716653"
---
# <a name="-imports-visual-basic"></a><span data-ttu-id="6860f-102">-Imports (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6860f-102">-imports (Visual Basic)</span></span>
<span data-ttu-id="6860f-103">Importa gli spazi dei nomi da un assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="6860f-103">Imports namespaces from a specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6860f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6860f-104">Syntax</span></span>  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a><span data-ttu-id="6860f-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6860f-105">Arguments</span></span>  
  
|<span data-ttu-id="6860f-106">Termine</span><span class="sxs-lookup"><span data-stu-id="6860f-106">Term</span></span>|<span data-ttu-id="6860f-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="6860f-107">Definition</span></span>|  
|---|---|  
|`namespaceList`|<span data-ttu-id="6860f-108">Richiesto.</span><span class="sxs-lookup"><span data-stu-id="6860f-108">Required.</span></span> <span data-ttu-id="6860f-109">Elenco delimitato da virgole di spazi dei nomi da importare.</span><span class="sxs-lookup"><span data-stu-id="6860f-109">Comma-delimited list of namespaces to be imported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6860f-110">Note</span><span class="sxs-lookup"><span data-stu-id="6860f-110">Remarks</span></span>  
 <span data-ttu-id="6860f-111">L'opzione `-imports` importa qualsiasi spazio dei nomi definito all'interno del set di file di origine corrente o da qualsiasi assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="6860f-111">The `-imports` option imports any namespace defined within the current set of source files or from any referenced assembly.</span></span>  
  
 <span data-ttu-id="6860f-112">I membri in uno spazio dei nomi specificato con `-imports` sono disponibili per tutti i file del codice sorgente nella compilazione.</span><span class="sxs-lookup"><span data-stu-id="6860f-112">The members in a namespace specified with `-imports` are available to all source-code files in the compilation.</span></span> <span data-ttu-id="6860f-113">Usare l' [istruzione Imports (tipo e spazio dei nomi .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) per usare uno spazio dei nomi in un unico file del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6860f-113">Use the [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to use a namespace in a single source-code file.</span></span>  
  
|<span data-ttu-id="6860f-114">Per impostare-Imports in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="6860f-114">To set -imports in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6860f-115">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="6860f-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6860f-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6860f-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6860f-117">2. fare clic sulla scheda **riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="6860f-117">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="6860f-118">3. Immettere il nome dello spazio dei nomi nella casella accanto al pulsante **Aggiungi importazione utente** .</span><span class="sxs-lookup"><span data-stu-id="6860f-118">3.  Enter the namespace name in the box beside the **Add User Import** button.</span></span><br /><span data-ttu-id="6860f-119">4. fare clic sul pulsante **Aggiungi importazione utente** .</span><span class="sxs-lookup"><span data-stu-id="6860f-119">4.  Click the **Add User Import** button.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6860f-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="6860f-120">Example</span></span>  
 <span data-ttu-id="6860f-121">Il codice seguente viene compilato quando si specifica `-imports:system.globalization`.</span><span class="sxs-lookup"><span data-stu-id="6860f-121">The following code compiles when `-imports:system.globalization` is specified.</span></span> <span data-ttu-id="6860f-122">In caso contrario, la compilazione riuscita richiede che un'istruzione `Imports System.Globalization` venga inclusa all'inizio del file di codice sorgente o che la proprietà sia completamente qualificata come `System.Globalization.CultureInfo.CurrentCulture.Name`.</span><span class="sxs-lookup"><span data-stu-id="6860f-122">Without it, successful compilation requires either that an `Imports System.Globalization` statement be included at the beginning of the source code file, or that the property be fully qualified as `System.Globalization.CultureInfo.CurrentCulture.Name`.</span></span>

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="6860f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6860f-123">See also</span></span>

- [<span data-ttu-id="6860f-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6860f-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6860f-125">Riferimenti e istruzione Imports</span><span class="sxs-lookup"><span data-stu-id="6860f-125">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="6860f-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="6860f-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
