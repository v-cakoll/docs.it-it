---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: d0a51b2af8b1d8fcf9f0df8dae457a0d3b570a1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744726"
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="8d80c-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d80c-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="8d80c-103">Indica al compilatore di non incorporare un manifesto dell'applicazione nel file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="8d80c-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d80c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d80c-104">Syntax</span></span>  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d80c-105">Note</span><span class="sxs-lookup"><span data-stu-id="8d80c-105">Remarks</span></span>  
 <span data-ttu-id="8d80c-106">Quando viene usata questa opzione, l'applicazione è soggetta a virtualizzazione in Windows Vista a meno che non venga specificato un manifesto dell'applicazione in un file di risorsa Win32 file o durante una istruzione di compilazione successiva.</span><span class="sxs-lookup"><span data-stu-id="8d80c-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="8d80c-107">Per altre informazioni sulla virtualizzazione, vedere [Distribuzione ClickOnce in Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="8d80c-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="8d80c-108">Per altre informazioni sulla creazione di manifesti, vedere [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8d80c-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d80c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d80c-109">See also</span></span>
- [<span data-ttu-id="8d80c-110">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8d80c-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8d80c-111">Pagina Applicazione, Creazione progetti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d80c-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
