---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
ms.openlocfilehash: ec4722cb7088819dae95ca1b7cbc1469d957a7aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400474"
---
# <a name="-removeintchecks"></a><span data-ttu-id="39e9d-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="39e9d-102">-removeintchecks</span></span>
<span data-ttu-id="39e9d-103">Attiva o disattiva il controllo degli errori di overflow per le operazioni integer.</span><span class="sxs-lookup"><span data-stu-id="39e9d-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39e9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39e9d-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="39e9d-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="39e9d-105">Arguments</span></span>  
  
|<span data-ttu-id="39e9d-106">Termine</span><span class="sxs-lookup"><span data-stu-id="39e9d-106">Term</span></span>|<span data-ttu-id="39e9d-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="39e9d-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="39e9d-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="39e9d-108">`+` &#124; `-`</span></span>|<span data-ttu-id="39e9d-109">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="39e9d-109">Optional.</span></span> <span data-ttu-id="39e9d-110">L' `-removeintchecks-` opzione fa sì che il compilatore verifichi tutti i calcoli Integer per gli errori di overflow.</span><span class="sxs-lookup"><span data-stu-id="39e9d-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="39e9d-111">Il valore predefinito è `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="39e9d-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="39e9d-112">Specifica `-removeintchecks` o `-removeintchecks+` impedisce il controllo degli errori ed è in grado di eseguire calcoli Integer più velocemente.</span><span class="sxs-lookup"><span data-stu-id="39e9d-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="39e9d-113">Tuttavia, senza il controllo degli errori e in caso di overflow delle capacità del tipo di dati, i risultati non corretti possono essere archiviati senza generare un errore.</span><span class="sxs-lookup"><span data-stu-id="39e9d-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="39e9d-114">Per impostare-removeintchecks (in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="39e9d-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="39e9d-115">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="39e9d-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="39e9d-116">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="39e9d-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="39e9d-117">2. fare clic sulla scheda **Compila** .</span><span class="sxs-lookup"><span data-stu-id="39e9d-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="39e9d-118">3. fare clic sul pulsante **Avanzate** .</span><span class="sxs-lookup"><span data-stu-id="39e9d-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="39e9d-119">4. modificare il valore della casella di **controllo Rimuovi overflow di Integer** .</span><span class="sxs-lookup"><span data-stu-id="39e9d-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="39e9d-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="39e9d-120">Example</span></span>  
 <span data-ttu-id="39e9d-121">Il codice seguente compila `Test.vb` e disattiva il controllo degli errori di overflow di Integer.</span><span class="sxs-lookup"><span data-stu-id="39e9d-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="39e9d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39e9d-122">See also</span></span>

- [<span data-ttu-id="39e9d-123">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="39e9d-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="39e9d-124">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="39e9d-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
