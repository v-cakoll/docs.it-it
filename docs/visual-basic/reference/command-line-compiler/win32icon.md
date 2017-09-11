---
title: /win32icon | Documenti di Microsoft
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
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: 13
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
ms.openlocfilehash: f7d451026438be722d6cb7eecfffe397ccff82ae
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="win32icon"></a><span data-ttu-id="46a7c-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="46a7c-102">/win32icon</span></span>
<span data-ttu-id="46a7c-103">Inserisce un file con estensione ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="46a7c-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="46a7c-104">Il file ICO rappresenta il file di output in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="46a7c-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46a7c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46a7c-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="46a7c-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="46a7c-106">Arguments</span></span>  
  
|<span data-ttu-id="46a7c-107">Termine</span><span class="sxs-lookup"><span data-stu-id="46a7c-107">Term</span></span>|<span data-ttu-id="46a7c-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="46a7c-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="46a7c-109">Il file ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="46a7c-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="46a7c-110">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="46a7c-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46a7c-111">Note</span><span class="sxs-lookup"><span data-stu-id="46a7c-111">Remarks</span></span>  
 <span data-ttu-id="46a7c-112">È possibile creare un file con estensione ico con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="46a7c-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="46a7c-113">Il compilatore di risorse viene richiamato quando si compila un programma Visual C++. viene creato un file con estensione ICO nel file RC.</span><span class="sxs-lookup"><span data-stu-id="46a7c-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="46a7c-114">Il `/win32icon` e `/win32resource` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="46a7c-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="46a7c-115">Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="46a7c-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span> <span data-ttu-id="46a7c-116">Vedere [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file. res.</span><span class="sxs-lookup"><span data-stu-id="46a7c-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="46a7c-117">Per impostare /win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="46a7c-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="46a7c-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="46a7c-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="46a7c-119">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="46a7c-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="46a7c-120">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="46a7c-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="46a7c-121">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="46a7c-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="46a7c-122">3.  Modificare il valore di **icona** casella.</span><span class="sxs-lookup"><span data-stu-id="46a7c-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46a7c-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="46a7c-123">Example</span></span>  
 <span data-ttu-id="46a7c-124">Il codice seguente Compila `In.vb` e aggiunge un file con estensione ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="46a7c-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="46a7c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46a7c-125">See Also</span></span>  
 <span data-ttu-id="46a7c-126">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="46a7c-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="46a7c-127"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="46a7c-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
