---
title: Limitazioni di Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d06b743996969dcd7fc022bbb8ab625f3a151137
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="d880b-102">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d880b-102">Visual Basic Limitations</span></span>
<span data-ttu-id="d880b-103">Le versioni precedenti di Visual Basic applicati limiti nel codice, ad esempio la lunghezza di nomi di variabili, il numero di variabili consentite nei moduli e le dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="d880b-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="d880b-104">In Visual Basic .NET, queste restrizioni sono stati ridotti, fornendo una maggiore libertà nella scrittura e il codice.</span><span class="sxs-lookup"><span data-stu-id="d880b-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="d880b-105">Limiti fisici sono dipendenti in memoria in fase di esecuzione di più sulle considerazioni relative alla fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d880b-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="d880b-106">Se si utilizzano le procedure di programmazione prudenti e dividono applicazioni di grandi dimensioni in più classi e moduli, è poche probabilità di che si verifichi un limite interno di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d880b-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="d880b-107">Di seguito sono alcune limitazioni che potrebbero verificarsi in casi estremi.</span><span class="sxs-lookup"><span data-stu-id="d880b-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="d880b-108">**Lunghezza del nome.**</span><span class="sxs-lookup"><span data-stu-id="d880b-108">**Name Length.**</span></span> <span data-ttu-id="d880b-109">È un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato.</span><span class="sxs-lookup"><span data-stu-id="d880b-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="d880b-110">Questo limite si applica a un'intera stringa di qualificazione se il nome dell'elemento è completo.</span><span class="sxs-lookup"><span data-stu-id="d880b-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="d880b-111">Vedere [nomi di elementi dichiarati](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="d880b-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="d880b-112">**Lunghezza della riga.**</span><span class="sxs-lookup"><span data-stu-id="d880b-112">**Line Length.**</span></span> <span data-ttu-id="d880b-113">È un massimo di 65535 caratteri in una riga fisica del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="d880b-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="d880b-114">La riga di codice sorgente logico può essere superiore se si utilizzano caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="d880b-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="d880b-115">Vedere [procedura: interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="d880b-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="d880b-116">**Dimensioni della matrice.**</span><span class="sxs-lookup"><span data-stu-id="d880b-116">**Array Dimensions.**</span></span> <span data-ttu-id="d880b-117">È un numero massimo delle dimensioni che è possibile dichiarare una matrice.</span><span class="sxs-lookup"><span data-stu-id="d880b-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="d880b-118">Questo limita il numero degli indici è possibile utilizzare per specificare un elemento di matrice.</span><span class="sxs-lookup"><span data-stu-id="d880b-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="d880b-119">Vedere [matrice di dimensioni in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="d880b-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="d880b-120">**Lunghezza della stringa.**</span><span class="sxs-lookup"><span data-stu-id="d880b-120">**String Length.**</span></span> <span data-ttu-id="d880b-121">È un numero massimo di caratteri Unicode, che è possibile archiviare in una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="d880b-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="d880b-122">Vedere [tipo di dati stringa](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d880b-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="d880b-123">**Lunghezza della stringa di ambiente.**</span><span class="sxs-lookup"><span data-stu-id="d880b-123">**Environment String Length.**</span></span> <span data-ttu-id="d880b-124">È un massimo di 32768 caratteri per qualsiasi stringa di ambiente utilizzato come argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d880b-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="d880b-125">Si tratta di una limitazione in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="d880b-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d880b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d880b-126">See Also</span></span>  
 [<span data-ttu-id="d880b-127">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="d880b-127">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="d880b-128">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d880b-128">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
