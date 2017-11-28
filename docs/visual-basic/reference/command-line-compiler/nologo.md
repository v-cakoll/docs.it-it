---
title: /nologo (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c2c7e7a111a3763d7463f67c2d984955da33bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="nologo-visual-basic"></a><span data-ttu-id="4f683-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f683-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="4f683-103">Evita la visualizzazione di informazioni sul copyright e sui messaggi informativi durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="4f683-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f683-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f683-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="4f683-105">Note</span><span class="sxs-lookup"><span data-stu-id="4f683-105">Remarks</span></span>  
 <span data-ttu-id="4f683-106">Se si specifica `/nologo`, il compilatore non visualizza informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="4f683-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="4f683-107">Per impostazione predefinita, l'opzione `/nologo` non è attiva.</span><span class="sxs-lookup"><span data-stu-id="4f683-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f683-108">Il `/nologo` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="4f683-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f683-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4f683-109">Example</span></span>  
 <span data-ttu-id="4f683-110">Il codice seguente Compila `T2.vb` e non visualizza informazioni sul copyright.</span><span class="sxs-lookup"><span data-stu-id="4f683-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f683-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f683-111">See Also</span></span>  
 [<span data-ttu-id="4f683-112">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f683-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="4f683-113">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="4f683-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
