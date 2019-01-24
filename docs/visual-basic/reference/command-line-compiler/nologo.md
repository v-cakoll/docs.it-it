---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 1b9cedc3e45795a66c203d4c86bb071045a1d3f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550474"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="4b5b1-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b5b1-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="4b5b1-103">Evita la visualizzazione del banner del copyright e i messaggi informativi durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b5b1-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b5b1-105">Note</span><span class="sxs-lookup"><span data-stu-id="4b5b1-105">Remarks</span></span>  
 <span data-ttu-id="4b5b1-106">Se si specifica `-nologo`, il compilatore non viene visualizzato un banner del copyright.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="4b5b1-107">Per impostazione predefinita, l'opzione `-nologo` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b5b1-108">Il `-nologo` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b5b1-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4b5b1-109">Example</span></span>  
 <span data-ttu-id="4b5b1-110">Il codice seguente Compila `T2.vb` e non viene visualizzato un banner del copyright.</span><span class="sxs-lookup"><span data-stu-id="4b5b1-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b5b1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b5b1-111">See also</span></span>
- [<span data-ttu-id="4b5b1-112">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b5b1-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="4b5b1-113">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4b5b1-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
