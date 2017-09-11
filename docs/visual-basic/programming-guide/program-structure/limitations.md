---
title: Limitazioni di Visual Basic | Documenti di Microsoft
ms.custom: 
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
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
ms.openlocfilehash: a3bd551ade2f0c55cd943cfbd353b09dfede4063
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-limitations"></a><span data-ttu-id="f31d0-102">Limitazioni di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f31d0-102">Visual Basic Limitations</span></span>
<span data-ttu-id="f31d0-103">Le versioni precedenti di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applicati limiti nel codice, ad esempio la lunghezza dei nomi di variabili, il numero di variabili consentite nei moduli e le dimensioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="f31d0-103">Earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="f31d0-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], ridotti queste restrizioni, fornendo una maggiore libertà nella scrittura e il codice.</span><span class="sxs-lookup"><span data-stu-id="f31d0-104">In [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="f31d0-105">I limiti fisici sono dipendenti più memoria in fase di esecuzione su considerazioni relative alla fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="f31d0-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="f31d0-106">Se si utilizzano le procedure di programmazione prudenti e dividono applicazioni di grandi dimensioni in più classi e moduli, è presente poche probabilità di incontrare interna [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitazione.</span><span class="sxs-lookup"><span data-stu-id="f31d0-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] limitation.</span></span>  
  
 <span data-ttu-id="f31d0-107">Di seguito sono alcune limitazioni che potrebbero verificarsi in casi estremi.</span><span class="sxs-lookup"><span data-stu-id="f31d0-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
-   <span data-ttu-id="f31d0-108">**Lunghezza del nome.**</span><span class="sxs-lookup"><span data-stu-id="f31d0-108">**Name Length.**</span></span> <span data-ttu-id="f31d0-109">Esiste un numero massimo di caratteri per il nome di ogni elemento di programmazione dichiarato.</span><span class="sxs-lookup"><span data-stu-id="f31d0-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="f31d0-110">Questo limite si applica a un'intera stringa di qualificazione se il nome dell'elemento è qualificato.</span><span class="sxs-lookup"><span data-stu-id="f31d0-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="f31d0-111">Vedere [dichiarati i nomi degli elementi](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f31d0-111">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   <span data-ttu-id="f31d0-112">**Lunghezza della riga.**</span><span class="sxs-lookup"><span data-stu-id="f31d0-112">**Line Length.**</span></span> <span data-ttu-id="f31d0-113">Esiste un massimo di 65535 caratteri in una riga fisica del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="f31d0-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="f31d0-114">La riga di codice sorgente logico può essere superiore se si utilizzano caratteri di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="f31d0-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="f31d0-115">Vedere [procedura: interrompere e combinare istruzioni nel codice](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f31d0-115">See [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
-   <span data-ttu-id="f31d0-116">**Dimensioni della matrice.**</span><span class="sxs-lookup"><span data-stu-id="f31d0-116">**Array Dimensions.**</span></span> <span data-ttu-id="f31d0-117">Esiste un numero massimo di dimensioni che è possibile dichiarare una matrice.</span><span class="sxs-lookup"><span data-stu-id="f31d0-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="f31d0-118">Questo limita il numero degli indici è possibile utilizzare per specificare un elemento di matrice.</span><span class="sxs-lookup"><span data-stu-id="f31d0-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="f31d0-119">Vedere [matrice dimensioni in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="f31d0-119">See [Array Dimensions in Visual Basic](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md).</span></span>  
  
-   <span data-ttu-id="f31d0-120">**Lunghezza della stringa.**</span><span class="sxs-lookup"><span data-stu-id="f31d0-120">**String Length.**</span></span> <span data-ttu-id="f31d0-121">Esiste un numero massimo di caratteri Unicode, che è possibile archiviare in una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="f31d0-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="f31d0-122">Vedere [tipo di dati stringa](../../../visual-basic/language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="f31d0-122">See [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md).</span></span>  
  
-   <span data-ttu-id="f31d0-123">**Lunghezza della stringa di ambiente.**</span><span class="sxs-lookup"><span data-stu-id="f31d0-123">**Environment String Length.**</span></span> <span data-ttu-id="f31d0-124">Esiste un massimo di 32768 caratteri per qualsiasi stringa di ambiente utilizzato come argomento della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="f31d0-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="f31d0-125">Si tratta di una limitazione in tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="f31d0-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31d0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f31d0-126">See Also</span></span>  
 <span data-ttu-id="f31d0-127">[Struttura del programma e convenzioni del codice](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f31d0-127">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="f31d0-128"> [Convenzioni di denominazione di Visual Basic](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span><span class="sxs-lookup"><span data-stu-id="f31d0-128"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)</span></span>
