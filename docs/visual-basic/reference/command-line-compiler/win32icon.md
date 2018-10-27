---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: afc35578f362f4a72a40fdb3d87406a8795cb59d
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194865"
---
# <a name="-win32icon"></a><span data-ttu-id="813b8-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="813b8-102">-win32icon</span></span>
<span data-ttu-id="813b8-103">Inserisce un file con estensione ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="813b8-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="813b8-104">Il file ICO rappresenta il file di output in **Esplora File**.</span><span class="sxs-lookup"><span data-stu-id="813b8-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="813b8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="813b8-105">Syntax</span></span>  
  
```  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="813b8-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="813b8-106">Arguments</span></span>  
  
|<span data-ttu-id="813b8-107">Termine</span><span class="sxs-lookup"><span data-stu-id="813b8-107">Term</span></span>|<span data-ttu-id="813b8-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="813b8-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="813b8-109">Il file con estensione ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="813b8-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="813b8-110">Racchiudere il nome file racchiuso tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="813b8-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="813b8-111">Note</span><span class="sxs-lookup"><span data-stu-id="813b8-111">Remarks</span></span>  
 <span data-ttu-id="813b8-112">È possibile creare un file con estensione ico con il compilatore di risorse (RC) di Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="813b8-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="813b8-113">Il compilatore di risorse viene richiamato quando si compila un programma in Visual C++. il file RC viene creato un file con estensione ico.</span><span class="sxs-lookup"><span data-stu-id="813b8-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="813b8-114">Il `-win32icon` e `-win32resource` opzioni si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="813b8-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="813b8-115">Visualizzare [- linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse, o [-risorse (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) collegare un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] file di risorse.</span><span class="sxs-lookup"><span data-stu-id="813b8-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span> <span data-ttu-id="813b8-116">Visualizzare [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="813b8-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="813b8-117">Per impostare - win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="813b8-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="813b8-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="813b8-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="813b8-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="813b8-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="813b8-120">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="813b8-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="813b8-121">3.  Modificare il valore di **icona** casella.</span><span class="sxs-lookup"><span data-stu-id="813b8-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="813b8-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="813b8-122">Example</span></span>  
 <span data-ttu-id="813b8-123">Il codice seguente Compila `In.vb` e associa un file con estensione ico, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="813b8-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="813b8-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="813b8-124">See Also</span></span>  
 [<span data-ttu-id="813b8-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="813b8-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="813b8-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="813b8-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
