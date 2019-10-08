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
# <a name="-rootnamespace"></a><span data-ttu-id="5f3b2-102">-rootnamespace</span><span class="sxs-lookup"><span data-stu-id="5f3b2-102">-rootnamespace</span></span>
<span data-ttu-id="5f3b2-103">Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3b2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f3b2-104">Syntax</span></span>  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f3b2-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5f3b2-105">Arguments</span></span>  
  
|<span data-ttu-id="5f3b2-106">Nome</span><span class="sxs-lookup"><span data-stu-id="5f3b2-106">Term</span></span>|<span data-ttu-id="5f3b2-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="5f3b2-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="5f3b2-108">Nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f3b2-109">Note</span><span class="sxs-lookup"><span data-stu-id="5f3b2-109">Remarks</span></span>  
 <span data-ttu-id="5f3b2-110">Se si utilizza il file eseguibile di Visual Studio (devenv. exe) per compilare un progetto creato in Visual Studio Integrated Development Environment, utilizzare `-rootnamespace` per specificare il valore della proprietà <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `-rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="5f3b2-111">Per ulteriori informazioni, vedere [Opzioni della riga di comando devenv](/visualstudio/ide/reference/devenv-command-line-switches) .</span><span class="sxs-lookup"><span data-stu-id="5f3b2-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="5f3b2-112">Usare il disassembler MSIL Common Language Runtime (`Ildasm.exe`) per visualizzare i nomi degli spazi dei nomi nel file di output.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="5f3b2-113">Per impostare-RootNamespace in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="5f3b2-113">To set -rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="5f3b2-114">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="5f3b2-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="5f3b2-116">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="5f3b2-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="5f3b2-117">3.  Modificare il valore nella casella **spazio dei nomi radice** .</span><span class="sxs-lookup"><span data-stu-id="5f3b2-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f3b2-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="5f3b2-118">Example</span></span>  
 <span data-ttu-id="5f3b2-119">Il codice seguente compila `In.vb` e racchiude tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="5f3b2-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f3b2-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3b2-120">See also</span></span>

- [<span data-ttu-id="5f3b2-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f3b2-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5f3b2-122">Ildasm.exe (Disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="5f3b2-122">Ildasm.exe (IL Disassembler)</span></span>](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="5f3b2-123">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="5f3b2-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
