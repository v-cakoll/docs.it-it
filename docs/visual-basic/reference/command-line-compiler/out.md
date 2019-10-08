---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
ms.openlocfilehash: 6b005ac26e3fffad350cb4ce52f7757c9fff2ac1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005339"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="7d736-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d736-102">-out (Visual Basic)</span></span>
<span data-ttu-id="7d736-103">Specifica il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="7d736-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d736-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d736-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="7d736-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7d736-105">Arguments</span></span>  
  
|<span data-ttu-id="7d736-106">Nome</span><span class="sxs-lookup"><span data-stu-id="7d736-106">Term</span></span>|<span data-ttu-id="7d736-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="7d736-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="7d736-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="7d736-108">Required.</span></span> <span data-ttu-id="7d736-109">Nome del file di output creato dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="7d736-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="7d736-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="7d736-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d736-111">Note</span><span class="sxs-lookup"><span data-stu-id="7d736-111">Remarks</span></span>  
 <span data-ttu-id="7d736-112">Specificare il nome completo e l'estensione del file da creare.</span><span class="sxs-lookup"><span data-stu-id="7d736-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="7d736-113">In caso contrario, il file con estensione exe prende il nome dal file del codice sorgente contenente la procedura `Sub Main` e il nome del file con estensione dll viene preso dal primo file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="7d736-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="7d736-114">Se si specifica un nome di file senza estensione exe o dll, il compilatore aggiunge automaticamente l'estensione, a seconda del valore specificato per l'opzione del compilatore `-target`.</span><span class="sxs-lookup"><span data-stu-id="7d736-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="7d736-115">Per impostare il Integrated Development Environment in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d736-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7d736-116">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="7d736-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7d736-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="7d736-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7d736-118">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="7d736-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="7d736-119">3.  Modificare il valore nella casella **nome assembly** .</span><span class="sxs-lookup"><span data-stu-id="7d736-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d736-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d736-120">Example</span></span>  
 <span data-ttu-id="7d736-121">Il codice seguente compila `T2.vb` e crea il file di output `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="7d736-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d736-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d736-122">See also</span></span>

- [<span data-ttu-id="7d736-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7d736-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7d736-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d736-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="7d736-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7d736-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
