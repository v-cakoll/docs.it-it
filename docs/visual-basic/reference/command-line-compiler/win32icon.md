---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 6b4b69d227c857442de6857fac023090b3698e81
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004638"
---
# <a name="-win32icon"></a><span data-ttu-id="7569e-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="7569e-102">-win32icon</span></span>
<span data-ttu-id="7569e-103">Inserisce un file con estensione ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="7569e-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="7569e-104">Il file ico rappresenta il file di output in **Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="7569e-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7569e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7569e-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="7569e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7569e-106">Arguments</span></span>  
  
|<span data-ttu-id="7569e-107">Nome</span><span class="sxs-lookup"><span data-stu-id="7569e-107">Term</span></span>|<span data-ttu-id="7569e-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="7569e-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="7569e-109">File con estensione ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="7569e-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="7569e-110">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="7569e-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7569e-111">Note</span><span class="sxs-lookup"><span data-stu-id="7569e-111">Remarks</span></span>  
 <span data-ttu-id="7569e-112">È possibile creare un file con estensione ico con il compilatore di risorse di Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="7569e-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="7569e-113">Il compilatore di risorse viene richiamato quando si compila C++ un programma Visual. un file con estensione ICO viene creato dal file RC.</span><span class="sxs-lookup"><span data-stu-id="7569e-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="7569e-114">Le opzioni `-win32icon` e `-win32resource` si escludono a vicenda.</span><span class="sxs-lookup"><span data-stu-id="7569e-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="7569e-115">Vedere [-linkresource ((Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) per alleghire un file di risorse .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7569e-115">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="7569e-116">Vedere [-win32resource (](../../../visual-basic/reference/command-line-compiler/win32resource.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="7569e-116">See [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="7569e-117">Per impostare-win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7569e-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="7569e-118">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="7569e-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7569e-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="7569e-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7569e-120">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="7569e-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="7569e-121">3.  Modificare il valore nella casella **icona** .</span><span class="sxs-lookup"><span data-stu-id="7569e-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7569e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="7569e-122">Example</span></span>  
 <span data-ttu-id="7569e-123">Il codice seguente compila `In.vb` e connette un file con estensione ICO, `Rf.ico`.</span><span class="sxs-lookup"><span data-stu-id="7569e-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7569e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7569e-124">See also</span></span>

- [<span data-ttu-id="7569e-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7569e-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7569e-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7569e-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
