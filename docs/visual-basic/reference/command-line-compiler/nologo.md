---
title: /nologo (Visual Basic) | Documenti di Microsoft
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
- -nologo compiler option [Visual Basic]
- banners, suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
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
ms.openlocfilehash: fe03c36f46717248269c9aaec13b40569161b0e0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="nologo-visual-basic"></a><span data-ttu-id="ced26-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ced26-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="ced26-103">Elimina visualizzazione di informazioni sul copyright e messaggi informativi durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="ced26-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ced26-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="ced26-105">Note</span><span class="sxs-lookup"><span data-stu-id="ced26-105">Remarks</span></span>  
 <span data-ttu-id="ced26-106">Se si specifica `/nologo`, il compilatore non visualizza informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="ced26-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="ced26-107">Per impostazione predefinita, l'opzione `/nologo` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="ced26-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ced26-108">Il `/nologo` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="ced26-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ced26-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ced26-109">Example</span></span>  
 <span data-ttu-id="ced26-110">Il codice seguente Compila `T2.vb` e non visualizza informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="ced26-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ced26-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ced26-111">See Also</span></span>  
 <span data-ttu-id="ced26-112">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ced26-112">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ced26-113"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="ced26-113"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
