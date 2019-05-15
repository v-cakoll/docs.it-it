---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 1c3c70b24de5163ca004b41a21017205a19d9730
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583368"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="1c2a4-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c2a4-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="1c2a4-103">Indica al compilatore di non riferimento automaticamente alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c2a4-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="1c2a4-105">Note</span><span class="sxs-lookup"><span data-stu-id="1c2a4-105">Remarks</span></span>  
 <span data-ttu-id="1c2a4-106">Il `-nostdlib` opzione rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="1c2a4-107">Il file Vbc. rsp, che si trova nella stessa directory del file Vbc.exe, fa riferimento all'assembly di .NET Framework comunemente utilizzati e Importa il `System` e `Microsoft.VisualBasic` gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c2a4-108">Gli assembly mscorlib. dll e VisualBasic vengono sempre fatto riferimento.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c2a4-109">Il `-nostdlib` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c2a4-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="1c2a4-110">Example</span></span>  
 <span data-ttu-id="1c2a4-111">Il codice seguente Compila `T2.vb` senza fare riferimento alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="1c2a4-112">È necessario impostare il `_MYTYPE` costante di compilazione condizionale per la stringa "Empty" per rimuovere il `My` oggetto.</span><span class="sxs-lookup"><span data-stu-id="1c2a4-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c2a4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c2a4-113">See also</span></span>

- [<span data-ttu-id="1c2a4-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="1c2a4-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="1c2a4-115">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c2a4-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1c2a4-116">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="1c2a4-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="1c2a4-117">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="1c2a4-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
