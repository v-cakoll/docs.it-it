---
title: /rootnamespace
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b02171b28034d676b7027e96c2c66e36be9ae604
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="rootnamespace"></a><span data-ttu-id="e42c8-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="e42c8-102">/rootnamespace</span></span>
<span data-ttu-id="e42c8-103">Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="e42c8-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e42c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e42c8-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="e42c8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e42c8-105">Arguments</span></span>  
  
|<span data-ttu-id="e42c8-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e42c8-106">Term</span></span>|<span data-ttu-id="e42c8-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e42c8-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="e42c8-108">Il nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="e42c8-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e42c8-109">Note</span><span class="sxs-lookup"><span data-stu-id="e42c8-109">Remarks</span></span>  
 <span data-ttu-id="e42c8-110">Se si utilizza il file eseguibile di Visual Studio (Devenv.exe) per compilare un progetto creato nell'ambiente di sviluppo integrato di Visual Studio, usare `/rootnamespace` per specificare il valore di <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e42c8-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="e42c8-111">Vedere [opzioni della riga di comando Devenv](/visualstudio/ide/reference/devenv-command-line-switches) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="e42c8-111">See [Devenv Command Line Switches](/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="e42c8-112">Utilizzare il Disassembler MSIL di common language runtime (`Ildasm.exe`) per visualizzare i nomi di spazio dei nomi nel file di output.</span><span class="sxs-lookup"><span data-stu-id="e42c8-112">Use the common language runtime MSIL Disassembler (`Ildasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="e42c8-113">Per impostare /rootnamespace in Visual Studio ambiente di sviluppo integrato.</span><span class="sxs-lookup"><span data-stu-id="e42c8-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e42c8-114">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="e42c8-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e42c8-115">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e42c8-115">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e42c8-116">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="e42c8-116">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="e42c8-117">3.  Modificare il valore di **radice Namespace** casella.</span><span class="sxs-lookup"><span data-stu-id="e42c8-117">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e42c8-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="e42c8-118">Example</span></span>  
 <span data-ttu-id="e42c8-119">Il codice seguente Compila `In.vb` e include tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="e42c8-119">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e42c8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e42c8-120">See Also</span></span>  
 [<span data-ttu-id="e42c8-121">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e42c8-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="e42c8-122">Ildasm.exe (Disassembler IL)</span><span class="sxs-lookup"><span data-stu-id="e42c8-122">Ildasm.exe (IL Disassembler)</span></span>](https://msdn.microsoft.com/library/f7dy01k1)  
 [<span data-ttu-id="e42c8-123">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="e42c8-123">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
