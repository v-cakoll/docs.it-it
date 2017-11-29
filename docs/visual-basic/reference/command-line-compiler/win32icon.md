---
title: /win32icon
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65149c617220966bc3bb6897d757a71cd60167d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="94e12-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="94e12-102">/win32icon</span></span>
<span data-ttu-id="94e12-103">Inserisce un file ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="94e12-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="94e12-104">Il file ICO rappresenta il file di output in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="94e12-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e12-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94e12-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="94e12-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="94e12-106">Arguments</span></span>  
  
|<span data-ttu-id="94e12-107">Termine</span><span class="sxs-lookup"><span data-stu-id="94e12-107">Term</span></span>|<span data-ttu-id="94e12-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="94e12-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="94e12-109">Il file ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="94e12-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="94e12-110">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="94e12-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e12-111">Note</span><span class="sxs-lookup"><span data-stu-id="94e12-111">Remarks</span></span>  
 <span data-ttu-id="94e12-112">È possibile creare un file ico con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="94e12-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="94e12-113">Il compilatore di risorse viene richiamato quando si compila un programma Visual C++. nel file RC, viene creato un file ico.</span><span class="sxs-lookup"><span data-stu-id="94e12-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="94e12-114">Il `/win32icon` e `/win32resource` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="94e12-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="94e12-115">Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="94e12-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="94e12-116">Vedere [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="94e12-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="94e12-117">Per impostare /win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94e12-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="94e12-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="94e12-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="94e12-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="94e12-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="94e12-120">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="94e12-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="94e12-121">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="94e12-121">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="94e12-122">3.  Modificare il valore di **icona** casella.</span><span class="sxs-lookup"><span data-stu-id="94e12-122">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="94e12-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="94e12-123">Example</span></span>  
 <span data-ttu-id="94e12-124">Il codice seguente Compila `In.vb` e allega un file ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="94e12-124">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="94e12-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e12-125">See Also</span></span>  
 [<span data-ttu-id="94e12-126">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="94e12-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="94e12-127">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="94e12-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
