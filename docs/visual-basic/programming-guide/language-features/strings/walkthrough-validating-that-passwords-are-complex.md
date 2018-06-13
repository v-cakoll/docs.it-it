---
title: Convalida della complessità delle password (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: acfc8ab958c8671ed7f1afd245d24a43ca12be29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650283"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="f629c-102">Procedura dettagliata: verifica della complessità delle password (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f629c-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="f629c-103">Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con informazioni sui controlli che la password non riesce.</span><span class="sxs-lookup"><span data-stu-id="f629c-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="f629c-104">Password può essere utilizzata in un sistema sicuro per autorizzare un utente.</span><span class="sxs-lookup"><span data-stu-id="f629c-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="f629c-105">Tuttavia, le password devono essere difficile per gli utenti non autorizzati di indovinare.</span><span class="sxs-lookup"><span data-stu-id="f629c-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="f629c-106">Gli utenti malintenzionati possono utilizzare un *attacco con dizionario* programma che scorre tutte le parole in un dizionario (o più dizionari in lingue diverse) e verifica se una delle parole funziona come una password.</span><span class="sxs-lookup"><span data-stu-id="f629c-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="f629c-107">Password vulnerabili, ad esempio "Yankees" o "Mustang sono facili" può essere individuata rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f629c-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="f629c-108">Password complesse, ad esempio "? È 'L1N3vaFiNdMeyeP@sSWerd! ", sono molto meno probabile che essere individuata.</span><span class="sxs-lookup"><span data-stu-id="f629c-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="f629c-109">Un sistema protetto da password è necessario assicurarsi che gli utenti scelgono di password complesse.</span><span class="sxs-lookup"><span data-stu-id="f629c-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="f629c-110">Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola.</span><span class="sxs-lookup"><span data-stu-id="f629c-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="f629c-111">In questo esempio viene illustrato come verificare la complessità.</span><span class="sxs-lookup"><span data-stu-id="f629c-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f629c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f629c-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="f629c-113">Codice</span><span class="sxs-lookup"><span data-stu-id="f629c-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f629c-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f629c-114">Compiling the Code</span></span>  
 <span data-ttu-id="f629c-115">Chiamare questo metodo passando la stringa che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="f629c-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="f629c-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f629c-116">This example requires:</span></span>  
  
-   <span data-ttu-id="f629c-117">Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="f629c-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="f629c-118">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="f629c-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="f629c-119">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="f629c-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="f629c-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="f629c-120">Security</span></span>  
 <span data-ttu-id="f629c-121">Se si sta spostando la password attraverso una rete, è necessario utilizzare un metodo sicuro per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="f629c-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="f629c-122">Per ulteriori informazioni, vedere [sicurezza delle applicazioni Web ASP.NET](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="f629c-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="f629c-123">È possibile migliorare l'accuratezza del `ValidatePassword` funzione tramite l'aggiunta di controlli di complessità aggiuntive:</span><span class="sxs-lookup"><span data-stu-id="f629c-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="f629c-124">Confrontare la password e le sue sottostringhe con il nome dell'utente, l'ID utente e un dizionario definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f629c-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="f629c-125">Inoltre, gestiscono visivamente simili caratteri come equivalenti quando si esegue il confronto.</span><span class="sxs-lookup"><span data-stu-id="f629c-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="f629c-126">Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".</span><span class="sxs-lookup"><span data-stu-id="f629c-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="f629c-127">Se è presente un solo carattere maiuscolo, assicurarsi che non è primo carattere della password.</span><span class="sxs-lookup"><span data-stu-id="f629c-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="f629c-128">Assicurarsi che gli ultimi due caratteri della password sono caratteri lettera.</span><span class="sxs-lookup"><span data-stu-id="f629c-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="f629c-129">Non consentire password nel quale sono inseriti tutti i simboli dalla prima riga della tastiera.</span><span class="sxs-lookup"><span data-stu-id="f629c-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f629c-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f629c-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="f629c-131">Protezione delle applicazioni Web ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f629c-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)
