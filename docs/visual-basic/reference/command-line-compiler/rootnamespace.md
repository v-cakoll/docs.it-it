---
title: /RootNamespace | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9a7a26407e981d3aea58d970d88bf25025e6bba6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="rootnamespace"></a><span data-ttu-id="9857c-102">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="9857c-102">/rootnamespace</span></span>
<span data-ttu-id="9857c-103">Specifica uno spazio dei nomi per tutte le dichiarazioni di tipo.</span><span class="sxs-lookup"><span data-stu-id="9857c-103">Specifies a namespace for all type declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9857c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9857c-104">Syntax</span></span>  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a><span data-ttu-id="9857c-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="9857c-105">Arguments</span></span>  
  
|<span data-ttu-id="9857c-106">Termine</span><span class="sxs-lookup"><span data-stu-id="9857c-106">Term</span></span>|<span data-ttu-id="9857c-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="9857c-107">Definition</span></span>|  
|---|---|  
|`namespace`|<span data-ttu-id="9857c-108">Il nome dello spazio dei nomi in cui racchiudere tutte le dichiarazioni di tipo per il progetto corrente.</span><span class="sxs-lookup"><span data-stu-id="9857c-108">The name of the namespace in which to enclose all type declarations for the current project.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9857c-109">Note</span><span class="sxs-lookup"><span data-stu-id="9857c-109">Remarks</span></span>  
 <span data-ttu-id="9857c-110">Se si utilizza il file eseguibile di Visual Studio (Devenv.exe) per compilare un progetto creato nell'ambiente di sviluppo integrato di Visual Studio, utilizzare `/rootnamespace` per specificare il valore di <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>proprietà.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="9857c-110">If you use the Visual Studio executable file (Devenv.exe) to compile a project created in the Visual Studio integrated development environment, use `/rootnamespace` to specify the value of the <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> property.</span></span> <span data-ttu-id="9857c-111">Vedere [opzioni della riga di comando Devenv](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="9857c-111">See [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) for more information.</span></span>  
  
 <span data-ttu-id="9857c-112">Utilizzare il Disassembler MSIL di common language runtime (I`ldasm.exe`) per visualizzare i nomi dello spazio dei nomi nel file di output.</span><span class="sxs-lookup"><span data-stu-id="9857c-112">Use the common language runtime MSIL Disassembler (I`ldasm.exe`) to view the namespace names in your output file.</span></span>  
  
|<span data-ttu-id="9857c-113">Per impostare /rootnamespace in Visual Studio ambiente di sviluppo integrato</span><span class="sxs-lookup"><span data-stu-id="9857c-113">To set /rootnamespace in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9857c-114">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="9857c-114">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9857c-115">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9857c-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9857c-116">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="9857c-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="9857c-117">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="9857c-117">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="9857c-118">3.  Modificare il valore di **radice Namespace** casella.</span><span class="sxs-lookup"><span data-stu-id="9857c-118">3.  Modify the value in the **Root Namespace** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9857c-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="9857c-119">Example</span></span>  
 <span data-ttu-id="9857c-120">Il codice seguente Compila `In.vb` e include tutte le dichiarazioni di tipo nello spazio dei nomi `mynamespace`.</span><span class="sxs-lookup"><span data-stu-id="9857c-120">The following code compiles `In.vb` and encloses all type declarations in the namespace `mynamespace`.</span></span>  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9857c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9857c-121">See Also</span></span>  
 <span data-ttu-id="9857c-122">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9857c-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9857c-123"> [Ildasm.exe (Disassembler IL)](https://msdn.microsoft.com/library/f7dy01k1) </span><span class="sxs-lookup"><span data-stu-id="9857c-123"> [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1) </span></span>  
<span data-ttu-id="9857c-124"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="9857c-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
