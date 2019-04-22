---
title: La convalida della complessità delle password (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 829d6485acdca22fbf10160c734e5c7f931dd855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58824936"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="50d13-102">Procedura dettagliata: Verifica della complesse delle password (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50d13-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="50d13-103">Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con le informazioni sui controlli che la password ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="50d13-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="50d13-104">Le password è utilizzabile in un sistema sicuro per autorizzare un utente.</span><span class="sxs-lookup"><span data-stu-id="50d13-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="50d13-105">Tuttavia, le password devono essere difficile per gli utenti non autorizzati di indovinare.</span><span class="sxs-lookup"><span data-stu-id="50d13-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="50d13-106">Gli utenti malintenzionati possono usare una *attacco con dizionario* programma che esegue l'iterazione attraverso tutte le parole in un dizionario (o più dizionari in diverse lingue) e verifica se una delle parole funziona come una password dell'utente.</span><span class="sxs-lookup"><span data-stu-id="50d13-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="50d13-107">Password vulnerabili, ad esempio "Yankees" o "Mustang" può essere individuata rapidamente.</span><span class="sxs-lookup"><span data-stu-id="50d13-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="50d13-108">Password più complesse, ad esempio "? Si 'L1N3vaFiNdMeyeP@sSWerd! ", sono molto meno probabile che essere scoperti.</span><span class="sxs-lookup"><span data-stu-id="50d13-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="50d13-109">Un sistema protetto da password è necessario assicurarsi che gli utenti scelgano le password complesse.</span><span class="sxs-lookup"><span data-stu-id="50d13-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="50d13-110">Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola.</span><span class="sxs-lookup"><span data-stu-id="50d13-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="50d13-111">In questo esempio viene illustrato come verificare la complessità.</span><span class="sxs-lookup"><span data-stu-id="50d13-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50d13-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="50d13-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="50d13-113">Codice</span><span class="sxs-lookup"><span data-stu-id="50d13-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50d13-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="50d13-114">Compiling the Code</span></span>  
 <span data-ttu-id="50d13-115">Chiamare questo metodo passando la stringa che contiene la password.</span><span class="sxs-lookup"><span data-stu-id="50d13-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="50d13-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="50d13-116">This example requires:</span></span>  
  
-   <span data-ttu-id="50d13-117">Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="50d13-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="50d13-118">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="50d13-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="50d13-119">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="50d13-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="50d13-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="50d13-120">Security</span></span>  
 <span data-ttu-id="50d13-121">Se stai spostando la password attraverso una rete, è necessario usare un metodo sicuro per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="50d13-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="50d13-122">Per altre informazioni, vedere [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="50d13-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="50d13-123">È possibile migliorare l'accuratezza del `ValidatePassword` funzione mediante l'aggiunta di controlli di complessità aggiuntiva:</span><span class="sxs-lookup"><span data-stu-id="50d13-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="50d13-124">Confronta le sottostringhe da un dizionario definito dall'applicazione, identificatore utente e il nome dell'utente e la password.</span><span class="sxs-lookup"><span data-stu-id="50d13-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="50d13-125">Considerare inoltre visivamente simili caratteri come equivalenti quando si esegue il confronto.</span><span class="sxs-lookup"><span data-stu-id="50d13-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="50d13-126">Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".</span><span class="sxs-lookup"><span data-stu-id="50d13-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="50d13-127">Se è presente un solo carattere maiuscolo, assicurarsi che non è primo carattere della password.</span><span class="sxs-lookup"><span data-stu-id="50d13-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="50d13-128">Assicurarsi che gli ultimi due caratteri della password sono caratteri letterali.</span><span class="sxs-lookup"><span data-stu-id="50d13-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="50d13-129">Non consentire password in cui vengono immessi tutti i simboli dalla prima riga della tastiera.</span><span class="sxs-lookup"><span data-stu-id="50d13-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50d13-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50d13-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="50d13-131">[Protezione delle applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50d13-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
