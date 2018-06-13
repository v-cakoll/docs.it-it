---
title: -out (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 234071d043b2649e2438ed20fe044fb89cdb9bf8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655889"
---
# <a name="-out-visual-basic"></a><span data-ttu-id="abe3b-102">-out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abe3b-102">-out (Visual Basic)</span></span>
<span data-ttu-id="abe3b-103">Specifica il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="abe3b-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="abe3b-104">Syntax</span></span>  
  
```  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="abe3b-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="abe3b-105">Arguments</span></span>  
  
|<span data-ttu-id="abe3b-106">Termine</span><span class="sxs-lookup"><span data-stu-id="abe3b-106">Term</span></span>|<span data-ttu-id="abe3b-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="abe3b-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="abe3b-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="abe3b-108">Required.</span></span> <span data-ttu-id="abe3b-109">Il nome del file di output, che il compilatore crea.</span><span class="sxs-lookup"><span data-stu-id="abe3b-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="abe3b-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="abe3b-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abe3b-111">Note</span><span class="sxs-lookup"><span data-stu-id="abe3b-111">Remarks</span></span>  
 <span data-ttu-id="abe3b-112">Specificare il nome completo e l'estensione del file da creare.</span><span class="sxs-lookup"><span data-stu-id="abe3b-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="abe3b-113">In caso contrario, il file .exe lo stesso nome file del codice sorgente che contiene il `Sub Main` procedure e il file DLL prende il nome del primo file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="abe3b-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="abe3b-114">Se si specifica un nome file senza estensione .exe o dll, il compilatore aggiunge automaticamente l'estensione per l'utente, a seconda del valore specificato per il `-target` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="abe3b-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `-target` compiler option.</span></span>  
  
|<span data-ttu-id="abe3b-115">Per impostare - out nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="abe3b-115">To set -out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="abe3b-116">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="abe3b-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="abe3b-117">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="abe3b-117">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="abe3b-118">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="abe3b-118">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="abe3b-119">3.  Modificare il valore di **nome Assembly** casella.</span><span class="sxs-lookup"><span data-stu-id="abe3b-119">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="abe3b-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="abe3b-120">Example</span></span>  
 <span data-ttu-id="abe3b-121">Il codice seguente Compila `T2.vb` e crea file di output `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="abe3b-121">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```console
vbc t2.vb -out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="abe3b-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="abe3b-122">See Also</span></span>  
 [<span data-ttu-id="abe3b-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="abe3b-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="abe3b-124">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="abe3b-124">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="abe3b-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="abe3b-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
