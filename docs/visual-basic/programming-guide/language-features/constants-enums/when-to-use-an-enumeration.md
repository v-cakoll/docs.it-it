---
title: Quando utilizzare un'enumerazione
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
ms.openlocfilehash: 5daae8d487ddfe079a54e305e59e32e8ded8f65e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353952"
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="9d0ae-102">Quando utilizzare un'enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9d0ae-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="9d0ae-103">Le enumerazioni offrono un modo semplice per usare set di costanti correlate.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="9d0ae-104">Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="9d0ae-105">Le enumerazioni vengono considerate come tipi di dati ed è possibile utilizzarle per creare set di costanti da utilizzare con le variabili e le proprietà.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="9d0ae-106">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="9d0ae-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="9d0ae-107">Ogni volta che una routine accetta un set limitato di variabili, è consigliabile utilizzare un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="9d0ae-108">Le enumerazioni rendono il codice più chiaro e leggibile, in particolare quando vengono utilizzati nomi significativi.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="9d0ae-109">I vantaggi dell'utilizzo delle enumerazioni includono:</span><span class="sxs-lookup"><span data-stu-id="9d0ae-109">The benefits of using enumerations include:</span></span>  
  
- <span data-ttu-id="9d0ae-110">Riduce gli errori causati dalla trasposizione o dalla digitazione errata dei numeri.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
- <span data-ttu-id="9d0ae-111">Semplifica la modifica dei valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-111">Makes it easy to change values in the future.</span></span>  
  
- <span data-ttu-id="9d0ae-112">Semplifica la lettura del codice, il che significa che è meno probabile che si verifichino errori.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
- <span data-ttu-id="9d0ae-113">Garantisce la compatibilità con le edizioni.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-113">Ensures forward compatibility.</span></span> <span data-ttu-id="9d0ae-114">Con le enumerazioni, è meno probabile che il codice abbia esito negativo se in futuro qualcuno modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="9d0ae-115">Enumerazioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="9d0ae-115">Naming Enumerations</span></span>  
 <span data-ttu-id="9d0ae-116">Usare una convenzione di denominazione per i membri dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="9d0ae-117">Quando Visual Basic rileva il nome di un membro di enumerazione, è possibile che venga generata un'eccezione se altre librerie dei tipi a cui viene fatto riferimento contengono lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-117">When Visual Basic encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="9d0ae-118">Usare un prefisso univoco che identifichi i valori dell'applicazione o del componente.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="9d0ae-119">Quando si fa riferimento a un membro di un'enumerazione, è necessario qualificare il nome del membro con il nome dell'enumerazione. in caso contrario, utilizzare l'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="9d0ae-120">Per altre informazioni, vedere [enumerazioni e qualificazione del nome](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="9d0ae-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="9d0ae-121">Enumerazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="9d0ae-121">Predefined Enumerations</span></span>  
 <span data-ttu-id="9d0ae-122">Visual Basic fornisce alcune enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResult`, per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="9d0ae-122">Visual Basic provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="9d0ae-123">Per un elenco di questi [, vedere costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="9d0ae-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d0ae-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d0ae-124">See also</span></span>

- [<span data-ttu-id="9d0ae-125">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="9d0ae-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="9d0ae-126">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="9d0ae-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="9d0ae-127">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="9d0ae-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="9d0ae-128">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9d0ae-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="9d0ae-129">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="9d0ae-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="9d0ae-130">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="9d0ae-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
- [<span data-ttu-id="9d0ae-131">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="9d0ae-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
