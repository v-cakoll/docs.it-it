---
title: "Convalida della complessità delle password (Visual Basic) | Documenti di Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
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
ms.openlocfilehash: 8d636c1e43de6a108cdc217cb21aaf7689e175f7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="916e6-102">Procedura dettagliata: verifica della complessità delle password (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="916e6-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="916e6-103">Questo metodo controlla alcune caratteristiche di password complesse e aggiorna un parametro di stringa con informazioni sui controlli che la password non riesce.</span><span class="sxs-lookup"><span data-stu-id="916e6-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="916e6-104">Le password è utilizzabile in un sistema sicuro per autorizzare un utente.</span><span class="sxs-lookup"><span data-stu-id="916e6-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="916e6-105">Tuttavia, le password devono essere difficile per gli utenti non autorizzati di indovinare.</span><span class="sxs-lookup"><span data-stu-id="916e6-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="916e6-106">Gli utenti malintenzionati possono utilizzare un *attacco con dizionario* programma che esegue l'iterazione attraverso tutte le parole in un dizionario (o più dizionari in lingue diverse), verifica se una delle parole funziona come password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="916e6-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="916e6-107">Password vulnerabili, ad esempio "Yankees" o "Mustang sono facili" può essere individuata rapidamente.</span><span class="sxs-lookup"><span data-stu-id="916e6-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="916e6-108">Password più complesse, ad esempio "? È 'L1N3vaFiNdMeyeP@sSWerd! ", molto meno probabilità di essere individuato.</span><span class="sxs-lookup"><span data-stu-id="916e6-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="916e6-109">Un sistema protetto da password è necessario assicurarsi che gli utenti scelgano password complesse.</span><span class="sxs-lookup"><span data-stu-id="916e6-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="916e6-110">Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola.</span><span class="sxs-lookup"><span data-stu-id="916e6-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="916e6-111">In questo esempio viene illustrato come verificare la complessità.</span><span class="sxs-lookup"><span data-stu-id="916e6-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="916e6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="916e6-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="916e6-113">Codice</span><span class="sxs-lookup"><span data-stu-id="916e6-113">Code</span></span>  
 <span data-ttu-id="916e6-114">[!code-vb[VbVbcnRegEx n.&1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="916e6-114">[!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="916e6-115">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="916e6-115">Compiling the Code</span></span>  
 <span data-ttu-id="916e6-116">Chiamare questo metodo passando la stringa che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="916e6-116">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="916e6-117">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="916e6-117">This example requires:</span></span>  
  
-   <span data-ttu-id="916e6-118">Accesso ai membri del <xref:System.Text.RegularExpressions>dello spazio dei nomi.</xref:System.Text.RegularExpressions></span><span class="sxs-lookup"><span data-stu-id="916e6-118">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="916e6-119">Aggiungere un `Imports` istruzione se non sono completamente qualifica i nomi dei membri nel codice.</span><span class="sxs-lookup"><span data-stu-id="916e6-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="916e6-120">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="916e6-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="916e6-121">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="916e6-121">Security</span></span>  
 <span data-ttu-id="916e6-122">Se si sta spostando la password attraverso una rete, è necessario utilizzare un metodo sicuro per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="916e6-122">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="916e6-123">Per ulteriori informazioni, vedere [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="916e6-123">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="916e6-124">È possibile migliorare l'accuratezza del `ValidatePassword` funzione mediante l'aggiunta di controlli di complessità supplementari:</span><span class="sxs-lookup"><span data-stu-id="916e6-124">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="916e6-125">Confrontare la password e le sue sottostringhe con il nome dell'utente, identificatore utente e un dizionario definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="916e6-125">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="916e6-126">Inoltre, gestiscono caratteri visivamente simili come equivalenti quando si esegue il confronto.</span><span class="sxs-lookup"><span data-stu-id="916e6-126">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="916e6-127">Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".</span><span class="sxs-lookup"><span data-stu-id="916e6-127">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="916e6-128">Se è presente un solo carattere maiuscolo, assicurarsi che non è primo carattere della password.</span><span class="sxs-lookup"><span data-stu-id="916e6-128">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="916e6-129">Assicurarsi che gli ultimi due caratteri della password sono caratteri lettera.</span><span class="sxs-lookup"><span data-stu-id="916e6-129">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="916e6-130">Non consentire password nel quale sono inseriti tutti i simboli dalla prima riga della tastiera.</span><span class="sxs-lookup"><span data-stu-id="916e6-130">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916e6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="916e6-131">See Also</span></span>  
 <span data-ttu-id="916e6-132"><xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="916e6-132"><xref:System.Text.RegularExpressions.Regex></span></span>   
<span data-ttu-id="916e6-133"> [Protezione delle applicazioni Web ASP.NET](https://msdn.microsoft.com/library/330a99hc)</span><span class="sxs-lookup"><span data-stu-id="916e6-133"> [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc)</span></span>
