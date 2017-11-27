---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a><span data-ttu-id="d14ac-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="d14ac-102">/removeintchecks</span></span>
<span data-ttu-id="d14ac-103">Attiva il controllo per le operazioni di tipo integer o disattivare l'errore di overflow.</span><span class="sxs-lookup"><span data-stu-id="d14ac-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d14ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d14ac-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d14ac-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d14ac-105">Arguments</span></span>  
  
|<span data-ttu-id="d14ac-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d14ac-106">Term</span></span>|<span data-ttu-id="d14ac-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d14ac-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d14ac-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d14ac-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d14ac-109">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d14ac-109">Optional.</span></span> <span data-ttu-id="d14ac-110">Il `/removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di integer per errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="d14ac-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="d14ac-111">Il valore predefinito è `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="d14ac-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="d14ac-112">Specifica di `/removeintchecks` o `/removeintchecks+` il controllo degli errori e rendere più veloci i calcoli di integer.</span><span class="sxs-lookup"><span data-stu-id="d14ac-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="d14ac-113">Tuttavia, senza errori, e se ha causato un overflow capacità di tipo di dati, senza che venga generato un errore potrebbero essere memorizzati risultati errati.</span><span class="sxs-lookup"><span data-stu-id="d14ac-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="d14ac-114">Per impostare /removeintchecks in Visual Studio ambiente di sviluppo integrato.</span><span class="sxs-lookup"><span data-stu-id="d14ac-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d14ac-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="d14ac-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d14ac-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d14ac-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d14ac-117">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="d14ac-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="d14ac-118">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="d14ac-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d14ac-119">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="d14ac-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d14ac-120">4.  Modificare il valore del **Rimuovi controllo dell'overflow di integer** casella.</span><span class="sxs-lookup"><span data-stu-id="d14ac-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d14ac-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="d14ac-121">Example</span></span>  
 <span data-ttu-id="d14ac-122">Il codice seguente Compila `Test.vb` e disattiva il controllo degli errori di overflow di integer.</span><span class="sxs-lookup"><span data-stu-id="d14ac-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d14ac-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d14ac-123">See Also</span></span>  
 [<span data-ttu-id="d14ac-124">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d14ac-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d14ac-125">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="d14ac-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
