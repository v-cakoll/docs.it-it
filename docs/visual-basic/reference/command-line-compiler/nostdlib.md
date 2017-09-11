---
title: /nostdlib (Visual Basic) | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 046e2b845324ed1c2f8c15bbb029fe84f7693f6e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="8c67c-102">/nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c67c-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="8c67c-103">Indica al compilatore di non automaticamente fare riferimento alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="8c67c-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c67c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c67c-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="8c67c-105">Note</span><span class="sxs-lookup"><span data-stu-id="8c67c-105">Remarks</span></span>  
 <span data-ttu-id="8c67c-106">Il `/nostdlib` opzione rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di lettura del file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="8c67c-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="8c67c-107">Tale file, che si trova nella stessa directory del file Vbc.exe: fa riferimento a quelle di uso comune [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly e le importazioni di `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8c67c-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c67c-108">Gli assembly mscorlib. dll e Microsoft.VisualBasic.dll fa sempre riferimento.</span><span class="sxs-lookup"><span data-stu-id="8c67c-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c67c-109">Il `/nostdlib` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8c67c-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c67c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c67c-110">Example</span></span>  
 <span data-ttu-id="8c67c-111">Il codice seguente Compila `T2.vb` senza fare riferimento alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="8c67c-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="8c67c-112">È necessario impostare il `_MYTYPE` costante di compilazione condizionale per la stringa "Empty" per rimuovere il `My` oggetto.</span><span class="sxs-lookup"><span data-stu-id="8c67c-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c67c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c67c-113">See Also</span></span>  
 <span data-ttu-id="8c67c-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="8c67c-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="8c67c-115"> [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8c67c-115"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8c67c-116"> [Esempi di righe di comando compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="8c67c-116"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="8c67c-117"> [Personalizzazione degli oggetti disponibili in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span><span class="sxs-lookup"><span data-stu-id="8c67c-117"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span></span>
