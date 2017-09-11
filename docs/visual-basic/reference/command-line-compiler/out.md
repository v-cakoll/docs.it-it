---
title: /out (Visual Basic) | Documenti di Microsoft
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
- /out compiler option [Visual Basic]
- -out compiler option [Visual Basic]
- out compiler option [Visual Basic]
ms.assetid: 9f148c15-0909-4cb8-a2db-777f8a8b45ae
caps.latest.revision: 17
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
ms.openlocfilehash: 489a9015718a581c793cd1217ba073625929daf3
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="out-visual-basic"></a><span data-ttu-id="18bbb-102">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18bbb-102">/out (Visual Basic)</span></span>
<span data-ttu-id="18bbb-103">Specifica il nome del file di output.</span><span class="sxs-lookup"><span data-stu-id="18bbb-103">Specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18bbb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18bbb-104">Syntax</span></span>  
  
```  
/out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="18bbb-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="18bbb-105">Arguments</span></span>  
  
|<span data-ttu-id="18bbb-106">Termine</span><span class="sxs-lookup"><span data-stu-id="18bbb-106">Term</span></span>|<span data-ttu-id="18bbb-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="18bbb-107">Definition</span></span>|  
|---|---|  
|`filename`|<span data-ttu-id="18bbb-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="18bbb-108">Required.</span></span> <span data-ttu-id="18bbb-109">Il nome del file di output, che il compilatore crea.</span><span class="sxs-lookup"><span data-stu-id="18bbb-109">The name of the output file the compiler creates.</span></span> <span data-ttu-id="18bbb-110">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="18bbb-110">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18bbb-111">Note</span><span class="sxs-lookup"><span data-stu-id="18bbb-111">Remarks</span></span>  
 <span data-ttu-id="18bbb-112">Specificare il nome completo e l'estensione del file da creare.</span><span class="sxs-lookup"><span data-stu-id="18bbb-112">Specify the full name and extension of the file to create.</span></span> <span data-ttu-id="18bbb-113">In caso contrario, il file .exe lo stesso nome file del codice sorgente che contiene il `Sub Main` procedure e il file DLL prende il nome del primo file di codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="18bbb-113">If you do not, the .exe file takes its name from the source-code file containing the `Sub Main` procedure, and the .dll file takes its name from the first source-code file.</span></span>  
  
 <span data-ttu-id="18bbb-114">Se si specifica un nome di file senza estensione .exe o. dll, il compilatore aggiunge automaticamente l'estensione, a seconda del valore specificato per il `/target` l'opzione del compilatore.</span><span class="sxs-lookup"><span data-stu-id="18bbb-114">If you specify a file name without an .exe or .dll extension, the compiler automatically adds the extension for you, depending on the value specified for the `/target` compiler option.</span></span>  
  
|<span data-ttu-id="18bbb-115">Per impostare /out nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="18bbb-115">To set /out in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="18bbb-116">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="18bbb-116">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="18bbb-117">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="18bbb-117">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="18bbb-118">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="18bbb-118">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="18bbb-119">2.  Fare clic sulla scheda **Applicazione** .</span><span class="sxs-lookup"><span data-stu-id="18bbb-119">2.  Click the **Application** tab.</span></span><br /><span data-ttu-id="18bbb-120">3.  Modificare il valore di **nome Assembly** casella.</span><span class="sxs-lookup"><span data-stu-id="18bbb-120">3.  Modify the value in the **Assembly Name** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="18bbb-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="18bbb-121">Example</span></span>  
 <span data-ttu-id="18bbb-122">Il codice seguente Compila `T2.vb` e crea file di output `T2.exe`.</span><span class="sxs-lookup"><span data-stu-id="18bbb-122">The following code compiles `T2.vb` and creates output file `T2.exe`.</span></span>  
  
```  
vbc t2.vb /out:t3.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="18bbb-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18bbb-123">See Also</span></span>  
 <span data-ttu-id="18bbb-124">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="18bbb-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="18bbb-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="18bbb-125"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="18bbb-126"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="18bbb-126"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
