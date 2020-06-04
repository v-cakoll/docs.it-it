---
title: -win32icon
ms.date: 03/13/2018
helpviewer_keywords:
- win32icon compiler option [Visual Basic]
- -win32icon compiler option [Visual Basic]
- /win32icon compiler option [Visual Basic]
ms.assetid: aecaab01-9353-46c5-941c-6edabd4eff92
ms.openlocfilehash: 52ef0b991554c800dba4320b0c64c81ddd1b0ff4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414285"
---
# <a name="-win32icon"></a><span data-ttu-id="0fe69-102">-win32icon</span><span class="sxs-lookup"><span data-stu-id="0fe69-102">-win32icon</span></span>
<span data-ttu-id="0fe69-103">Inserisce un file con estensione ICO nel file di output.</span><span class="sxs-lookup"><span data-stu-id="0fe69-103">Inserts an .ico file in the output file.</span></span> <span data-ttu-id="0fe69-104">Il file ico rappresenta il file di output in **Esplora file**.</span><span class="sxs-lookup"><span data-stu-id="0fe69-104">This .ico file represents the output file in **File Explorer**.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe69-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0fe69-105">Syntax</span></span>  
  
```console  
-win32icon:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fe69-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0fe69-106">Arguments</span></span>  
  
|<span data-ttu-id="0fe69-107">Termine</span><span class="sxs-lookup"><span data-stu-id="0fe69-107">Term</span></span>|<span data-ttu-id="0fe69-108">Definizione</span><span class="sxs-lookup"><span data-stu-id="0fe69-108">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="0fe69-109">File con estensione ico da aggiungere al file di output.</span><span class="sxs-lookup"><span data-stu-id="0fe69-109">The .ico file to add to your output file.</span></span> <span data-ttu-id="0fe69-110">Racchiudere il nome file tra virgolette ("") se contiene uno spazio.</span><span class="sxs-lookup"><span data-stu-id="0fe69-110">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fe69-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="0fe69-111">Remarks</span></span>  
 <span data-ttu-id="0fe69-112">È possibile creare un file con estensione ico con il compilatore di risorse di Microsoft Windows (RC).</span><span class="sxs-lookup"><span data-stu-id="0fe69-112">You can create an .ico file with the Microsoft Windows Resource Compiler (RC).</span></span> <span data-ttu-id="0fe69-113">Il compilatore di risorse viene richiamato quando si compila un programma di Visual C++; un file con estensione ICO viene creato dal file RC.</span><span class="sxs-lookup"><span data-stu-id="0fe69-113">The resource compiler is invoked when you compile a Visual C++ program; an .ico file is created from the .rc file.</span></span> <span data-ttu-id="0fe69-114">Le opzioni `-win32icon` e `-win32resource` si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="0fe69-114">The `-win32icon` and `-win32resource` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="0fe69-115">Vedere [-linkresource ((Visual Basic)](linkresource.md) per fare riferimento a un file di risorse .NET Framework o [-Resource (Visual Basic)](resource.md) per alleghire un file di risorse .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0fe69-115">See [-linkresource (Visual Basic)](linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](resource.md) to attach a .NET Framework resource file.</span></span> <span data-ttu-id="0fe69-116">Vedere [-win32resource (](win32resource.md) per importare un file con estensione res.</span><span class="sxs-lookup"><span data-stu-id="0fe69-116">See [-win32resource](win32resource.md) to import a .res file.</span></span>  
  
|<span data-ttu-id="0fe69-117">Per impostare-win32icon nell'IDE di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0fe69-117">To set -win32icon in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0fe69-118">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="0fe69-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0fe69-119">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="0fe69-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0fe69-120">2. fare clic sulla scheda **applicazione** .</span><span class="sxs-lookup"><span data-stu-id="0fe69-120">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="0fe69-121">3. modificare il valore nella casella **icona** .</span><span class="sxs-lookup"><span data-stu-id="0fe69-121">3.  Modify the value in the **Icon** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0fe69-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="0fe69-122">Example</span></span>  
 <span data-ttu-id="0fe69-123">Il codice seguente compila `In.vb` e connette un file con estensione ico `Rf.ico` .</span><span class="sxs-lookup"><span data-stu-id="0fe69-123">The following code compiles `In.vb` and attaches an .ico file, `Rf.ico`.</span></span>  
  
```console
vbc -win32icon:rf.ico in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fe69-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0fe69-124">See also</span></span>

- [<span data-ttu-id="0fe69-125">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fe69-125">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="0fe69-126">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="0fe69-126">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
