---
title: Quando utilizzare un'enumerazione (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: enumerations [Visual Basic]
ms.assetid: e6e47b5b-3ed9-452d-a481-9c3fed88519a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3b2937cc71c0c31bd8dce3d77fb33f48e1b5750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-use-an-enumeration-visual-basic"></a><span data-ttu-id="24832-102">Quando utilizzare un'enumerazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24832-102">When to Use an Enumeration (Visual Basic)</span></span>
<span data-ttu-id="24832-103">Enumerazioni offrono un modo semplice per utilizzare i set di costanti correlate.</span><span class="sxs-lookup"><span data-stu-id="24832-103">Enumerations offer an easy way to work with sets of related constants.</span></span> <span data-ttu-id="24832-104">Un'enumerazione, o `Enum`, è un nome simbolico per un set di valori.</span><span class="sxs-lookup"><span data-stu-id="24832-104">An enumeration, or `Enum`, is a symbolic name for a set of values.</span></span> <span data-ttu-id="24832-105">Le enumerazioni sono considerate come tipi di dati e utilizzarli per creare set di costanti per l'utilizzo con variabili e proprietà.</span><span class="sxs-lookup"><span data-stu-id="24832-105">Enumerations are treated as data types, and you can use them to create sets of constants for use with variables and properties.</span></span>  
  
## <a name="when-to-use-an-enumeration"></a><span data-ttu-id="24832-106">Quando utilizzare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="24832-106">When to Use an Enumeration</span></span>  
 <span data-ttu-id="24832-107">Ogni volta che una stored procedure accetta un set limitato di variabili, è possibile utilizzare un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="24832-107">Whenever a procedure accepts a limited set of variables, consider using an enumeration.</span></span> <span data-ttu-id="24832-108">Le enumerazioni rendono il codice più chiaro e più leggibile, soprattutto quando vengono utilizzati nomi significativi.</span><span class="sxs-lookup"><span data-stu-id="24832-108">Enumerations make for clearer and more readable code, particularly when meaningful names are used.</span></span>  
  
 <span data-ttu-id="24832-109">I vantaggi dell'utilizzo di enumerazioni includono:</span><span class="sxs-lookup"><span data-stu-id="24832-109">The benefits of using enumerations include:</span></span>  
  
-   <span data-ttu-id="24832-110">Per ridurre gli errori causati dalla trasposizione o numeri di errori di digitazione.</span><span class="sxs-lookup"><span data-stu-id="24832-110">Reduces errors caused by transposing or mistyping numbers.</span></span>  
  
-   <span data-ttu-id="24832-111">Consente di modificare i valori in futuro.</span><span class="sxs-lookup"><span data-stu-id="24832-111">Makes it easy to change values in the future.</span></span>  
  
-   <span data-ttu-id="24832-112">Rende il codice più facile da leggere, pertanto che è meno probabile che gli errori al suo interno.</span><span class="sxs-lookup"><span data-stu-id="24832-112">Makes code easier to read, which means it is less likely that errors will creep into it.</span></span>  
  
-   <span data-ttu-id="24832-113">Garantisce la compatibilità.</span><span class="sxs-lookup"><span data-stu-id="24832-113">Ensures forward compatibility.</span></span> <span data-ttu-id="24832-114">Con enumerazioni, il codice è meno probabile che se in futuro un utente modifica i valori corrispondenti ai nomi dei membri.</span><span class="sxs-lookup"><span data-stu-id="24832-114">With enumerations, your code is less likely to fail if in the future someone changes the values corresponding to the member names.</span></span>  
  
## <a name="naming-enumerations"></a><span data-ttu-id="24832-115">Denominazione delle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="24832-115">Naming Enumerations</span></span>  
 <span data-ttu-id="24832-116">Utilizzare una convenzione di denominazione per i membri di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="24832-116">Use a naming convention for enumeration members.</span></span> <span data-ttu-id="24832-117">Quando [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene rilevato un nome di membro di enumerazione, potrebbe essere generata un'eccezione se altre librerie dei tipi di riferimento contengono lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="24832-117">When [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] encounters an enumeration member name, an exception may be thrown if other referenced type libraries contain the same name.</span></span> <span data-ttu-id="24832-118">Utilizzare un prefisso univoco che identifica i valori di un'applicazione o componente.</span><span class="sxs-lookup"><span data-stu-id="24832-118">Use a unique prefix that identifies the values from your application or component.</span></span>  
  
 <span data-ttu-id="24832-119">Quando si fa riferimento a un membro di enumerazione, è necessario qualificare il nome del membro con il nome di enumerazione o utilizzare il `Imports` istruzione.</span><span class="sxs-lookup"><span data-stu-id="24832-119">When referring to a member of an enumeration, you must qualify the member name with the enumeration name or else use the `Imports` statement.</span></span> <span data-ttu-id="24832-120">Per ulteriori informazioni, vedere [qualifica di nomi ed enumerazioni](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="24832-120">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
## <a name="predefined-enumerations"></a><span data-ttu-id="24832-121">Enumerazioni predefinite</span><span class="sxs-lookup"><span data-stu-id="24832-121">Predefined Enumerations</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="24832-122">fornisce un numero di enumerazioni predefinite, ad esempio `FirstDayOfWeek` e `MsgBoxResult`, per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="24832-122"> provides a number of predefined enumerations, such as `FirstDayOfWeek` and `MsgBoxResult`, to facilitate your code.</span></span> <span data-ttu-id="24832-123">Per un elenco di tali vedere [costanti ed enumerazioni](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="24832-123">For a list of these see [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24832-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24832-124">See Also</span></span>  
 [<span data-ttu-id="24832-125">Procedura: dichiarare un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="24832-125">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="24832-126">Procedura: Fare riferimento a un membro di enumerazione</span><span class="sxs-lookup"><span data-stu-id="24832-126">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="24832-127">Qualifica di nomi ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="24832-127">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="24832-128">Procedura: scorrere un'enumerazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24832-128">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="24832-129">Procedura: Determinare la stringa associata a un valore di enumerazione</span><span class="sxs-lookup"><span data-stu-id="24832-129">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="24832-130">Istruzione Enum</span><span class="sxs-lookup"><span data-stu-id="24832-130">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [<span data-ttu-id="24832-131">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="24832-131">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
