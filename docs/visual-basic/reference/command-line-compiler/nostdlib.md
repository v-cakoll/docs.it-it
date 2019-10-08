---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 819505df2e7d5f93302f9ed601de856e36ed7124
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005409"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="7884f-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7884f-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="7884f-103">Fa in modo che il compilatore non faccia automaticamente riferimento alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="7884f-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7884f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7884f-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="7884f-105">Note</span><span class="sxs-lookup"><span data-stu-id="7884f-105">Remarks</span></span>  
 <span data-ttu-id="7884f-106">L'opzione `-nostdlib` rimuove il riferimento automatico all'assembly System. dll e impedisce al compilatore di leggere il file Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="7884f-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="7884f-107">Il file Vbc. rsp, che si trova nella stessa directory del file Vbc. exe, fa riferimento agli assembly di .NET Framework di uso comune e importa gli spazi dei nomi `System` e `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="7884f-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7884f-108">Viene sempre fatto riferimento agli assembly mscorlib. dll e Microsoft. VisualBasic. dll.</span><span class="sxs-lookup"><span data-stu-id="7884f-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7884f-109">L'opzione `-nostdlib` non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="7884f-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7884f-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7884f-110">Example</span></span>  
 <span data-ttu-id="7884f-111">Il codice seguente compila `T2.vb` senza fare riferimento alle librerie standard.</span><span class="sxs-lookup"><span data-stu-id="7884f-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="7884f-112">È necessario impostare la costante di compilazione condizionale `_MYTYPE` sulla stringa "Empty" per rimuovere l'oggetto `My`.</span><span class="sxs-lookup"><span data-stu-id="7884f-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7884f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7884f-113">See also</span></span>

- [<span data-ttu-id="7884f-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="7884f-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="7884f-115">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7884f-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7884f-116">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="7884f-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="7884f-117">Personalizzazione degli oggetti disponibili in My</span><span class="sxs-lookup"><span data-stu-id="7884f-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
