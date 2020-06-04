---
title: Costanti ed enumerazioni
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- Visual Basic code, constants
- constants [Visual Basic]
- object libraries, Object Browser
- Visual Basic code, enumerations
- declaring constants [Visual Basic], enumerations
- naming conventions [Visual Basic], constants
- Visual Basic code, improving readability with constants
ms.assetid: c8aba36e-fa47-4a33-8b68-cb2009218270
ms.openlocfilehash: 7d15c46c0f6bb00c23dd98e464f61a5f94b0773a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414402"
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="6950b-102">Costanti ed enumerazioni in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6950b-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="6950b-103">Le costanti consentono di usare nomi significativi al posto di un valore che non cambia.</span><span class="sxs-lookup"><span data-stu-id="6950b-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="6950b-104">Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6950b-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="6950b-105">È possibile usare le costanti per specificare nomi descrittivi, anziché numeri, rendendo il codice più leggibile.</span><span class="sxs-lookup"><span data-stu-id="6950b-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="6950b-106">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="6950b-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="6950b-107">Ad esempio, si può dichiarare un'enumerazione per un set di costanti integer associate ai giorni della settimana e quindi usare i nomi dei giorni anziché i relativi valori integer nel codice.</span><span class="sxs-lookup"><span data-stu-id="6950b-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6950b-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6950b-108">In This Section</span></span>  
  
|<span data-ttu-id="6950b-109">Termine</span><span class="sxs-lookup"><span data-stu-id="6950b-109">Term</span></span>|<span data-ttu-id="6950b-110">Definizione</span><span class="sxs-lookup"><span data-stu-id="6950b-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="6950b-111">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="6950b-111">Constants Overview</span></span>](constants-overview.md)|<span data-ttu-id="6950b-112">Gli argomenti di questa sezione descrivono le costanti e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6950b-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="6950b-113">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="6950b-113">Enumerations Overview</span></span>](enumerations-overview.md)|<span data-ttu-id="6950b-114">Gli argomenti di questa sezione descrivono le enumerazioni e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6950b-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="6950b-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6950b-115">Related Sections</span></span>  
  
|<span data-ttu-id="6950b-116">Termine</span><span class="sxs-lookup"><span data-stu-id="6950b-116">Term</span></span>|<span data-ttu-id="6950b-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="6950b-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="6950b-118">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="6950b-118">Const Statement</span></span>](../../../language-reference/statements/const-statement.md)|<span data-ttu-id="6950b-119">Viene descritta l'istruzione `Const`, usata per dichiarare le costanti.</span><span class="sxs-lookup"><span data-stu-id="6950b-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="6950b-120">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="6950b-120">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)|<span data-ttu-id="6950b-121">Viene descritta l'istruzione `Enum`, usata per creare le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="6950b-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="6950b-122">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="6950b-122">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="6950b-123">Viene descritta l'istruzione `Option Explicit`, usata a livello di modulo per imporre la dichiarazione esplicita di tutte le variabili di tale modulo.</span><span class="sxs-lookup"><span data-stu-id="6950b-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="6950b-124">Option Infer (istruzione)</span><span class="sxs-lookup"><span data-stu-id="6950b-124">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)|<span data-ttu-id="6950b-125">Viene descritta l'istruzione `Option Infer`, che abilita l'uso dell'inferenza del tipo di variabile locale nelle variabili dichiaranti.</span><span class="sxs-lookup"><span data-stu-id="6950b-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="6950b-126">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="6950b-126">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)|<span data-ttu-id="6950b-127">Viene descritta l'istruzione `Option Strict`, che limita le conversioni implicite di tipi di dati sollo alle conversioni verso tipi di dati più grandi, non consente l'associazione tardiva né la tipizzazione implicita che genera un tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="6950b-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
