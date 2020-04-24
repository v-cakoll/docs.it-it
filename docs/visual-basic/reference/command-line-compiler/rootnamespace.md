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
ms.openlocfilehash: 4df4e74fc13c922f51f5b74c3c152bdea28b4431
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005205"
---
# <a name="-rootnamespace"></a><span data-ttu-id="70b7e-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="70b7e-102">-rootnamespace</span></span>
<span data-ttu-id="70b7e-103">Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="70b7e-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70b7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="70b7e-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="70b7e-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="70b7e-105">Arguments</span></span>  
  
|<span data-ttu-id="70b7e-106">Termine</span><span class="sxs-lookup"><span data-stu-id="70b7e-106">Term</span></span>|<span data-ttu-id="70b7e-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="70b7e-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="70b7e-108">Nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="70b7e-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70b7e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="70b7e-109">Remarks</span></span>  
 <span data-ttu-id="70b7e-110">Se si utilizza il file eseguibile di Visual Studio (devenv. exe) per compilare un progetto creato in Visual Studio Integrated Development Environment, `-rootnamespace` utilizzare per specificare il valore della <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="70b7e-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="70b7e-111">Per ulteriori informazioni, vedere [Opzioni della riga di comando devenv](/visualstudio/ide/reference/devenv-command-line-switches) .</span><span class="sxs-lookup"><span data-stu-id="70b7e-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="70b7e-112">Usare il disassembler MSIL di Common Language Runtime`Ildasm.exe`() per visualizzare i nomi degli spazi dei nomi nel file di output.</span><span class="sxs-lookup"><span data-stu-id="70b7e-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="70b7e-113">Per impostare-RootNamespace in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="70b7e-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="70b7e-114">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="70b7e-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="70b7e-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="70b7e-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="70b7e-116">2. fare clic sulla scheda **applicazione** .</span><span class="sxs-lookup"><span data-stu-id="70b7e-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="70b7e-117">3. modificare il valore nella casella **spazio dei nomi radice** .</span><span class="sxs-lookup"><span data-stu-id="70b7e-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="70b7e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="70b7e-118">Example</span></span>  
 <span data-ttu-id="70b7e-119">Il codice seguente compila `In.vb` e racchiude tutte le dichiarazioni di tipo nello spazio dei nomi. `mynamespace`</span><span class="sxs-lookup"><span data-stu-id="70b7e-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="70b7e-120">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="70b7e-120">See also</span></span>

- [<span data-ttu-id="70b7e-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="70b7e-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="70b7e-122">Ildasm. exe (disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="70b7e-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="70b7e-123">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="70b7e-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
