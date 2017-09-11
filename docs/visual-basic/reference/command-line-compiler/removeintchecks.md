---
title: /removeintchecks | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 25f67774238c6e9a6b3a2c50b3702e43d5a6374c
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="removeintchecks"></a><span data-ttu-id="342d0-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="342d0-102">/removeintchecks</span></span>
<span data-ttu-id="342d0-103">Attiva il controllo per le operazioni di tipo integer o disattivare l'errore di overflow.</span><span class="sxs-lookup"><span data-stu-id="342d0-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="342d0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="342d0-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="342d0-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="342d0-105">Arguments</span></span>  
  
|<span data-ttu-id="342d0-106">Termine</span><span class="sxs-lookup"><span data-stu-id="342d0-106">Term</span></span>|<span data-ttu-id="342d0-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="342d0-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="342d0-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="342d0-108">`+` &#124; `-`</span></span>|<span data-ttu-id="342d0-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="342d0-109">Optional.</span></span> <span data-ttu-id="342d0-110">Il `/removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli integer per errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="342d0-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="342d0-111">Il valore predefinito è `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="342d0-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="342d0-112">Specifica di `/removeintchecks` o `/removeintchecks+` il controllo degli errori e rendere integer risultano più rapide.</span><span class="sxs-lookup"><span data-stu-id="342d0-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="342d0-113">Tuttavia, senza errori, e se ha causato un overflow capacità di tipo di dati, possono essere memorizzati risultati errati senza che venga generato un errore.</span><span class="sxs-lookup"><span data-stu-id="342d0-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="342d0-114">Per impostare /removeintchecks in Visual Studio ambiente di sviluppo integrato</span><span class="sxs-lookup"><span data-stu-id="342d0-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="342d0-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="342d0-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="342d0-116">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="342d0-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="342d0-117">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="342d0-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="342d0-118">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="342d0-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="342d0-119">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="342d0-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="342d0-120">4.  Modificare il valore di **Rimuovi controllo dell'overflow di integer** casella.</span><span class="sxs-lookup"><span data-stu-id="342d0-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="342d0-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="342d0-121">Example</span></span>  
 <span data-ttu-id="342d0-122">Il codice seguente Compila `Test.vb` e consente di disattivare il controllo dell'overflow integer.</span><span class="sxs-lookup"><span data-stu-id="342d0-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="342d0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="342d0-123">See Also</span></span>  
 <span data-ttu-id="342d0-124">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="342d0-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="342d0-125"> [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="342d0-125"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
