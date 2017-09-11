---
title: Quando utilizzare un&quot;enumerazione (Visual Basic) | Documenti di Microsoft
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
- enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: 12
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
ms.openlocfilehash: 3853950382fd4336c569f9d772aea3c1312f2ebc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="2e131-102">Quando utilizzare un'enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e131-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="2e131-103">Enumerazioni offrono un modo semplice per l'utilizzo di set di costanti correlate.</span><span class="sxs-lookup"><span data-stu-id="2e131-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="2e131-104">Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori.</span><span class="sxs-lookup"><span data-stu-id="2e131-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="2e131-105">Le enumerazioni sono considerate come tipi di dati e utilizzarli per creare set di costanti per l'utilizzo con variabili e proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e131-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="2e131-106">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="2e131-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="2e131-107">Ogni volta che una routine accetta un numero limitato di variabili, è consigliabile utilizzare un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2e131-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="2e131-108">Le enumerazioni rendono il codice più chiaro e più leggibile, soprattutto quando vengono utilizzati nomi significativi.</span><span class="sxs-lookup"><span data-stu-id="2e131-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="2e131-109">I vantaggi dell'utilizzo di enumerazioni includono:</span><span class="sxs-lookup"><span data-stu-id="2e131-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="2e131-110">Per ridurre gli errori causati dalla trasposizione o digitazione di numeri.</span><span class="sxs-lookup"><span data-stu-id="2e131-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="2e131-111">Consente di modificare i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="2e131-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="2e131-112">Rende il codice più leggibile, ciò significa che è meno probabile che gli errori al suo interno.</span><span class="sxs-lookup"><span data-stu-id="2e131-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="2e131-113">Garantisce la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="2e131-113">Ensures forward compatibility.</span></span> <span data-ttu-id="2e131-114">Con enumerazioni, il codice è meno probabile che non venga completata se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="2e131-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="2e131-115">Denominazione delle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="2e131-115">Naming Enumerations</span></span>  
 <span data-ttu-id="2e131-116">Utilizzare una convenzione di denominazione per i membri di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="2e131-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="2e131-117">Quando [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] viene rilevato un nome di membro di enumerazione, potrebbe essere generata un'eccezione se altre librerie dei tipi di riferimento contengono lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2e131-117">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="2e131-118">Utilizzare un prefisso univoco che identifica i valori di un'applicazione o componente.</span><span class="sxs-lookup"><span data-stu-id="2e131-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="2e131-119">Quando si fa riferimento a un membro di enumerazione, è necessario qualificare il nome del membro con il nome di enumerazione o utilizzare il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="2e131-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="2e131-120">Per ulteriori informazioni, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="2e131-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="2e131-121">Enumerazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="2e131-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2e131-122">fornisce un numero di enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResul`t, per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="2e131-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResul`t, to facilitate your code.</span></span> <span data-ttu-id="2e131-123">Per un elenco di questi vedere [costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="2e131-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e131-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e131-124">See Also</span></span>  
 <span data-ttu-id="2e131-125">[Procedura: dichiarare un'enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-125">[How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="2e131-126"> [Procedura: fare riferimento a un membro di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-126"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="2e131-127"> [Qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-127"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="2e131-128"> [Procedura: scorrere un'enumerazione in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-128"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="2e131-129"> [Procedura: determinare la stringa associata a un valore di enumerazione](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-129"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="2e131-130"> [Istruzione Enum](../../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2e131-130"> [Enum Statement](../../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="2e131-131"> [Costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="2e131-131"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
