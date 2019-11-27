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
ms.openlocfilehash: 858f22df26d44f47848921ee862c1d4c1ca1fc60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353980"
---
# <a name="constants-and-enumerations-in-visual-basic"></a><span data-ttu-id="2c8fa-102">Costanti ed enumerazioni in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2c8fa-102">Constants and Enumerations in Visual Basic</span></span>
<span data-ttu-id="2c8fa-103">Le costanti consentono di usare nomi significativi al posto di un valore che non cambia.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-103">Constants are a way to use meaningful names in place of a value that does not change.</span></span> <span data-ttu-id="2c8fa-104">Archiviano i valori che, come suggerisce il nome, rimangono costanti durante l'esecuzione di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="2c8fa-105">È possibile usare le costanti per specificare nomi descrittivi, anziché numeri, rendendo il codice più leggibile.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-105">You can use constants to provide meaningful names, instead of numbers, making your code more readable.</span></span>  
  
 <span data-ttu-id="2c8fa-106">Le enumerazioni offrono un modo pratico per usare i set di costanti correlate e per associare i valori delle costanti ai nomi.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-106">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="2c8fa-107">Ad esempio, si può dichiarare un'enumerazione per un set di costanti integer associate ai giorni della settimana e quindi usare i nomi dei giorni anziché i relativi valori integer nel codice.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-107">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c8fa-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="2c8fa-108">In This Section</span></span>  
  
|<span data-ttu-id="2c8fa-109">Termine</span><span class="sxs-lookup"><span data-stu-id="2c8fa-109">Term</span></span>|<span data-ttu-id="2c8fa-110">Definizione</span><span class="sxs-lookup"><span data-stu-id="2c8fa-110">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="2c8fa-111">Cenni preliminari sulle costanti</span><span class="sxs-lookup"><span data-stu-id="2c8fa-111">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)|<span data-ttu-id="2c8fa-112">Gli argomenti di questa sezione descrivono le costanti e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-112">Topics in this section describe constants and their uses.</span></span>|  
|[<span data-ttu-id="2c8fa-113">Cenni preliminari sulle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="2c8fa-113">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)|<span data-ttu-id="2c8fa-114">Gli argomenti di questa sezione descrivono le enumerazioni e il relativo utilizzo.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-114">Topics in this section describe enumerations and their uses.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="2c8fa-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="2c8fa-115">Related Sections</span></span>  
  
|<span data-ttu-id="2c8fa-116">Termine</span><span class="sxs-lookup"><span data-stu-id="2c8fa-116">Term</span></span>|<span data-ttu-id="2c8fa-117">Definizione</span><span class="sxs-lookup"><span data-stu-id="2c8fa-117">Definition</span></span>|  
|---|---|  
|[<span data-ttu-id="2c8fa-118">Istruzione Const</span><span class="sxs-lookup"><span data-stu-id="2c8fa-118">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="2c8fa-119">Viene descritta l'istruzione `Const`, usata per dichiarare le costanti.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-119">Describes the `Const` statement, which is used to declare constants.</span></span>|  
|[<span data-ttu-id="2c8fa-120">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="2c8fa-120">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)|<span data-ttu-id="2c8fa-121">Viene descritta l'istruzione `Enum`, usata per creare le enumerazioni.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-121">Describes the `Enum` statement, which is used to create enumerations.</span></span>|  
|[<span data-ttu-id="2c8fa-122">Istruzione Option Explicit</span><span class="sxs-lookup"><span data-stu-id="2c8fa-122">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)|<span data-ttu-id="2c8fa-123">Viene descritta l'istruzione `Option Explicit`, usata a livello di modulo per imporre la dichiarazione esplicita di tutte le variabili di tale modulo.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-123">Describes the `Option Explicit` statement, which is used at module level to force explicit declaration of all variables in that module.</span></span>|  
|[<span data-ttu-id="2c8fa-124">Istruzione Option Infer</span><span class="sxs-lookup"><span data-stu-id="2c8fa-124">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)|<span data-ttu-id="2c8fa-125">Viene descritta l'istruzione `Option Infer`, che abilita l'uso dell'inferenza del tipo di variabile locale nelle variabili dichiaranti.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-125">Describes the `Option Infer` statement, which enables the use of local type inference in declaring variables.</span></span>|  
|[<span data-ttu-id="2c8fa-126">Istruzione Option Strict</span><span class="sxs-lookup"><span data-stu-id="2c8fa-126">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="2c8fa-127">Viene descritta l'istruzione `Option Strict`, che limita le conversioni implicite di tipi di dati sollo alle conversioni verso tipi di dati più grandi, non consente l'associazione tardiva né la tipizzazione implicita che genera un tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="2c8fa-127">Describes the `Option Strict` statement, which restricts implicit data type conversions to only widening conversions, disallows late binding, and disallows implicit typing that results in an `Object` type.</span></span>|
