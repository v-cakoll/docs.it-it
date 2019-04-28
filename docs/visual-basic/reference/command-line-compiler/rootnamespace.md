---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
ms.openlocfilehash: ff4b1729f1b9fb1d698b4b5b1e3711ce3d27b4db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61639035"
---
# <a name="-rootnamespace"></a><span data-ttu-id="73b54-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="73b54-102">-rootnamespace</span></span>
<span data-ttu-id="73b54-103">Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="73b54-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73b54-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73b54-104">Syntax</span></span>  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="73b54-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="73b54-105">Arguments</span></span>  
  
|<span data-ttu-id="73b54-106">Termine</span><span class="sxs-lookup"><span data-stu-id="73b54-106">Term</span></span>|<span data-ttu-id="73b54-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="73b54-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="73b54-108">Il nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="73b54-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73b54-109">Note</span><span class="sxs-lookup"><span data-stu-id="73b54-109">Remarks</span></span>  
 <span data-ttu-id="73b54-110">Se si usa il file eseguibile (Devenv.exe) di Visual Studio per compilare un progetto creato nell'ambiente di sviluppo integrato di Visual Studio, usare `-rootnamespace` per specificare il valore della <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="73b54-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="73b54-111">Visualizzare [opzioni della riga di comando Devenv](/visualstudio/ide/reference/devenv-command-line-switches) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="73b54-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="73b54-112">Usare common language runtime MSIL Disassembler (`Ildasm.exe`) per visualizzare i nomi dello spazio dei nomi nel file di output.</span><span class="sxs-lookup"><span data-stu-id="73b54-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="73b54-113">Per impostare-. rootnamespace nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="73b54-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="73b54-114">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="73b54-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="73b54-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="73b54-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="73b54-116">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="73b54-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="73b54-117">3.  Modificare il valore di **radice Namespace** casella.</span><span class="sxs-lookup"><span data-stu-id="73b54-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="73b54-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="73b54-118">Example</span></span>  
 <span data-ttu-id="73b54-119">Il codice seguente Compila `In.vb` racchiude tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="73b54-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="73b54-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73b54-120">See also</span></span>

- [<span data-ttu-id="73b54-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73b54-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="73b54-122">Ildasm.exe (Disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="73b54-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="73b54-123">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="73b54-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
