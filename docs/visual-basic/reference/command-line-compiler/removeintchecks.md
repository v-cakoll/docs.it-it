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
ms.openlocfilehash: f061497083dc23fd07f61108938a4129c0af5f3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188533"
---
# <a name="-removeintchecks"></a><span data-ttu-id="881e7-102">-/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="881e7-102">-removeintchecks</span></span>
<span data-ttu-id="881e7-103">Attiva il controllo per operazioni con numeri interi o disattivare l'errore di overflow.</span><span class="sxs-lookup"><span data-stu-id="881e7-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="881e7-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="881e7-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="881e7-105">Arguments</span></span>  
  
|<span data-ttu-id="881e7-106">Termine</span><span class="sxs-lookup"><span data-stu-id="881e7-106">Term</span></span>|<span data-ttu-id="881e7-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="881e7-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="881e7-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="881e7-108">`+` &#124; `-`</span></span>|<span data-ttu-id="881e7-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="881e7-109">Optional.</span></span> <span data-ttu-id="881e7-110">Il `-removeintchecks-` opzione indica al compilatore di verificare tutti i calcoli di interi per gli errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="881e7-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="881e7-111">Il valore predefinito è `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="881e7-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="881e7-112">Che specifica `-removeintchecks` o `-removeintchecks+` impedisce il controllo degli errori e può rendere più veloci i calcoli di integer.</span><span class="sxs-lookup"><span data-stu-id="881e7-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="881e7-113">Tuttavia, senza il controllo degli errori, e se le capacità di tipo di dati sono ha causato l'overflow, risultati non corretti potrebbero essere archiviati senza generare un errore.</span><span class="sxs-lookup"><span data-stu-id="881e7-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="881e7-114">Per impostare - /removeintchecks nell'ambiente di sviluppo integrato di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="881e7-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="881e7-115">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="881e7-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="881e7-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="881e7-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="881e7-117">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="881e7-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="881e7-118">3.  Fare clic su **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="881e7-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="881e7-119">4.  Modificare il valore dei **Rimuovi controllo dell'overflow integer** casella.</span><span class="sxs-lookup"><span data-stu-id="881e7-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="881e7-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="881e7-120">Example</span></span>  
 <span data-ttu-id="881e7-121">Il codice seguente Compila `Test.vb` e consente di disattivare il controllo dell'overflow integer.</span><span class="sxs-lookup"><span data-stu-id="881e7-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="881e7-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="881e7-122">See Also</span></span>  
 [<span data-ttu-id="881e7-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="881e7-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="881e7-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="881e7-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
