---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 07e1718554b158635b9d8b04958834e804e1fe9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964383"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="22174-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22174-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="22174-103">Evita la visualizzazione del banner sul copyright e dei messaggi informativi durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="22174-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22174-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22174-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="22174-105">Note</span><span class="sxs-lookup"><span data-stu-id="22174-105">Remarks</span></span>  
 <span data-ttu-id="22174-106">Se si specifica `-nologo`, il compilatore non visualizza un banner sul copyright.</span><span class="sxs-lookup"><span data-stu-id="22174-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="22174-107">Per impostazione predefinita, l'opzione `-nologo` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="22174-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22174-108">L' `-nologo` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="22174-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22174-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="22174-109">Example</span></span>  
 <span data-ttu-id="22174-110">Il codice seguente compila `T2.vb` e non visualizza un banner sul copyright.</span><span class="sxs-lookup"><span data-stu-id="22174-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="22174-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22174-111">See also</span></span>

- [<span data-ttu-id="22174-112">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22174-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="22174-113">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="22174-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
