---
title: Convalida della complessità delle password
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 7b2d6a81f5dc88688a469b96d56a098a2b45c59f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363685"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="cb2d6-102">Procedura dettagliata: verifica della complessità delle password (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb2d6-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="cb2d6-103">Questo metodo verifica la presenza di alcune caratteristiche di password complesse e aggiorna un parametro di stringa con informazioni sui controlli che la password ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="cb2d6-104">Le password possono essere utilizzate in un sistema sicuro per autorizzare un utente.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="cb2d6-105">Tuttavia, le password devono essere difficili da indovinare per utenti non autorizzati.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="cb2d6-106">Gli utenti malintenzionati possono usare un programma di *attacco del dizionario* , che scorre tutte le parole in un dizionario (o più dizionari in linguaggi diversi) e verifica se una delle parole funziona come la password di un utente.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="cb2d6-107">È possibile indovinare rapidamente password vulnerabili, ad esempio "Yankee" o "Mustang".</span><span class="sxs-lookup"><span data-stu-id="cb2d6-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="cb2d6-108">Password più complesse, ad esempio "? È L1N3vaFiNdMeyeP@sSWerd molto meno probabile che venga indovinato.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="cb2d6-109">Un sistema protetto da password deve garantire che gli utenti scelgano password complesse.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="cb2d6-110">Una password complessa è complessa (contenente una combinazione di caratteri maiuscoli, minuscoli, numerici e speciali) e non è una parola.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="cb2d6-111">Questo esempio illustra come verificare la complessità.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb2d6-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="cb2d6-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="cb2d6-113">Codice</span><span class="sxs-lookup"><span data-stu-id="cb2d6-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="cb2d6-114">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="cb2d6-114">Compile the code</span></span>  
 <span data-ttu-id="cb2d6-115">Chiamare questo metodo passando la stringa che contiene tale password.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="cb2d6-116">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb2d6-116">This example requires:</span></span>  
  
- <span data-ttu-id="cb2d6-117">Accedere ai membri dello spazio dei nomi <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="cb2d6-118">Aggiungere un'istruzione `Imports` se i nomi dei membri all'interno del codice non sono specificati in modo completo.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="cb2d6-119">Per altre informazioni, vedere [Istruzione Imports (tipo e spazio dei nomi .NET)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="cb2d6-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="cb2d6-120">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="cb2d6-120">Security</span></span>  
 <span data-ttu-id="cb2d6-121">Se si sta migrando la password in una rete, è necessario usare un metodo sicuro per il trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="cb2d6-122">Per altre informazioni, vedere [sicurezza dell'applicazione Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="cb2d6-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="cb2d6-123">Per migliorare l'accuratezza della `ValidatePassword` funzione, è possibile aggiungere ulteriori controlli di complessità:</span><span class="sxs-lookup"><span data-stu-id="cb2d6-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="cb2d6-124">Confrontare la password e le relative sottostringhe con il nome dell'utente, l'identificatore utente e un dizionario definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="cb2d6-125">Inoltre, quando si eseguono i confronti, i caratteri visivi simili sono considerati equivalenti.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="cb2d6-126">Ad esempio, considerare le lettere "l" e "e" come equivalenti ai numeri "1" e "3".</span><span class="sxs-lookup"><span data-stu-id="cb2d6-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="cb2d6-127">Se è presente un solo carattere maiuscolo, assicurarsi che non sia il primo carattere della password.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="cb2d6-128">Verificare che gli ultimi due caratteri della password siano caratteri letterali.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="cb2d6-129">Non consentire le password in cui tutti i simboli vengono immessi dalla riga superiore della tastiera.</span><span class="sxs-lookup"><span data-stu-id="cb2d6-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2d6-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb2d6-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="cb2d6-131">[Protezione delle applicazioni Web ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cb2d6-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
