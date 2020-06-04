---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: d1307603ebc06b4eb4c3786f1cd2fb432c0cf636
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360462"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="50e65-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50e65-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="50e65-103">Evita la visualizzazione del banner sul copyright e dei messaggi informativi durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="50e65-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50e65-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="50e65-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="50e65-105">Remarks</span></span>  
 <span data-ttu-id="50e65-106">Se si specifica `-nologo` , il compilatore non visualizza un banner sul copyright.</span><span class="sxs-lookup"><span data-stu-id="50e65-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="50e65-107">Per impostazione predefinita, l'opzione `-nologo` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="50e65-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50e65-108">L' `-nologo` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="50e65-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50e65-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="50e65-109">Example</span></span>  
 <span data-ttu-id="50e65-110">Il codice seguente compila `T2.vb` e non visualizza un banner sul copyright.</span><span class="sxs-lookup"><span data-stu-id="50e65-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="50e65-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50e65-111">See also</span></span>

- [<span data-ttu-id="50e65-112">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50e65-112">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="50e65-113">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="50e65-113">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
