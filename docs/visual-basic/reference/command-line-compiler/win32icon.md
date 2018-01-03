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
ms.openlocfilehash: 4fc5210d2dcf30d9c4603b67b890c78510af1338
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="win32icon"></a><span data-ttu-id="ce15b-102">/win32icon</span><span class="sxs-lookup"><span data-stu-id="ce15b-102">/win32icon</span></span>
<span data-ttu-id="ce15b-103">Inserisce un file ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="ce15b-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="ce15b-104">Il file ICO rappresenta il file di output in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="ce15b-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce15b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce15b-105">Syntax</span></span>  
  
```  
/win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ce15b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ce15b-106">Arguments</span></span>  
  
|<span data-ttu-id="ce15b-107">Termine</span><span class="sxs-lookup"><span data-stu-id="ce15b-107">Term</span></span>|<span data-ttu-id="ce15b-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="ce15b-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="ce15b-109">Il file ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="ce15b-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="ce15b-110">Racchiudere il nome del file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="ce15b-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce15b-111">Note</span><span class="sxs-lookup"><span data-stu-id="ce15b-111">Remarks</span></span>  
 <span data-ttu-id="ce15b-112">È possibile creare un file ico con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="ce15b-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="ce15b-113">Il compilatore di risorse viene richiamato quando si compila un programma Visual C++. nel file RC, viene creato un file ico.</span><span class="sxs-lookup"><span data-stu-id="ce15b-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="ce15b-114">Il `/win32icon` e `/win32resource` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="ce15b-114">The `/win32icon` and `/win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="ce15b-115">Vedere [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="ce15b-115">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="ce15b-116">Vedere [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="ce15b-116">See [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="ce15b-117">Per impostare /win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ce15b-117">To set /win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="ce15b-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="ce15b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ce15b-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="ce15b-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="ce15b-120">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="ce15b-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="ce15b-121">3.  Modificare il valore di **icona** casella.</span><span class="sxs-lookup"><span data-stu-id="ce15b-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ce15b-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="ce15b-122">Example</span></span>  
 <span data-ttu-id="ce15b-123">Il codice seguente Compila `In.vb` e allega un file ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="ce15b-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```  
vbc /win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce15b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce15b-124">See Also</span></span>  
 [<span data-ttu-id="ce15b-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ce15b-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ce15b-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="ce15b-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
