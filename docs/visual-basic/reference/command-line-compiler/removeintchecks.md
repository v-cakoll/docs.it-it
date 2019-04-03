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
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822726"
---
# <a name="-removeintchecks"></a><span data-ttu-id="290a8-102">-/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="290a8-102">-removeintchecks</span></span>
<span data-ttu-id="290a8-103">Attiva il controllo per operazioni con numeri interi o disattivare l'errore di overflow.</span><span class="sxs-lookup"><span data-stu-id="290a8-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="290a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="290a8-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="290a8-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="290a8-105">Arguments</span></span>  
  
|<span data-ttu-id="290a8-106">Termine</span><span class="sxs-lookup"><span data-stu-id="290a8-106">Term</span></span>|<span data-ttu-id="290a8-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="290a8-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="290a8-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="290a8-108">`+` &#124; `-`</span></span>|<span data-ttu-id="290a8-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="290a8-109">Optional.</span></span> <span data-ttu-id="290a8-110">Il `-removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di interi per gli errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="290a8-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="290a8-111">Il valore predefinito è `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="290a8-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="290a8-112">Che specifica `-removeintchecks` o `-removeintchecks+` impedisce il controllo degli errori e può rendere più veloci i calcoli di integer.</span><span class="sxs-lookup"><span data-stu-id="290a8-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="290a8-113">Tuttavia, senza il controllo degli errori, e se le capacità di tipo di dati sono ha causato l'overflow, risultati non corretti potrebbero essere archiviati senza generare un errore.</span><span class="sxs-lookup"><span data-stu-id="290a8-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="290a8-114">Per impostare - /removeintchecks nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="290a8-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="290a8-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="290a8-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="290a8-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="290a8-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="290a8-117">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="290a8-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="290a8-118">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="290a8-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="290a8-119">4.  Modificare il valore dei **Rimuovi controllo dell'overflow integer** casella.</span><span class="sxs-lookup"><span data-stu-id="290a8-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="290a8-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="290a8-120">Example</span></span>  
 <span data-ttu-id="290a8-121">Il codice seguente Compila `Test.vb` e consente di disattivare il controllo dell'overflow integer.</span><span class="sxs-lookup"><span data-stu-id="290a8-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="290a8-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="290a8-122">See also</span></span>

- [<span data-ttu-id="290a8-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="290a8-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="290a8-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="290a8-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
