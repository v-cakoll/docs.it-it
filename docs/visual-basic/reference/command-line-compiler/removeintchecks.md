---
title: -/removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26485fe2ba3f5647266147744cbe53f978694a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656126"
---
# <a name="-removeintchecks"></a><span data-ttu-id="8be3a-102">-/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="8be3a-102">-removeintchecks</span></span>
<span data-ttu-id="8be3a-103">Attiva il controllo per le operazioni di tipo integer o disattivare l'errore di overflow.</span><span class="sxs-lookup"><span data-stu-id="8be3a-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8be3a-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8be3a-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8be3a-105">Arguments</span></span>  
  
|<span data-ttu-id="8be3a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="8be3a-106">Term</span></span>|<span data-ttu-id="8be3a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="8be3a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="8be3a-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="8be3a-108">`+` &#124; `-`</span></span>|<span data-ttu-id="8be3a-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8be3a-109">Optional.</span></span> <span data-ttu-id="8be3a-110">Il `-removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di integer per errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="8be3a-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="8be3a-111">Il valore predefinito è `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="8be3a-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="8be3a-112">Specifica di `-removeintchecks` o `-removeintchecks+` il controllo degli errori e rendere più veloci i calcoli di integer.</span><span class="sxs-lookup"><span data-stu-id="8be3a-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="8be3a-113">Tuttavia, senza errori, e se ha causato un overflow capacità di tipo di dati, senza che venga generato un errore potrebbero essere memorizzati risultati errati.</span><span class="sxs-lookup"><span data-stu-id="8be3a-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="8be3a-114">Per impostare - /removeintchecks nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8be3a-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="8be3a-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="8be3a-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8be3a-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="8be3a-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="8be3a-117">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="8be3a-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="8be3a-118">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="8be3a-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="8be3a-119">4.  Modificare il valore del **Rimuovi controllo dell'overflow di integer** casella.</span><span class="sxs-lookup"><span data-stu-id="8be3a-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8be3a-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="8be3a-120">Example</span></span>  
 <span data-ttu-id="8be3a-121">Il codice seguente Compila `Test.vb` e disattiva il controllo degli errori di overflow di integer.</span><span class="sxs-lookup"><span data-stu-id="8be3a-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8be3a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8be3a-122">See Also</span></span>  
 [<span data-ttu-id="8be3a-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8be3a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8be3a-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="8be3a-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
