---
title: Sicurezza e input dell'utente
description: Il codice potrebbe passare i dati immessi dall'utente come parametri ad altro codice, il che può influire sulla sicurezza. È possibile eseguire il controllo dell'intervallo per rifiutare l'input problematico.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: fa9f8d4708e928c51e446d8369c9b4556fc6fb77
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186112"
---
# <a name="security-and-user-input"></a><span data-ttu-id="9c8ca-104">Sicurezza e input dell'utente</span><span class="sxs-lookup"><span data-stu-id="9c8ca-104">Security and User Input</span></span>

<span data-ttu-id="9c8ca-105">I dati utente, ovvero tutti i tipi di input, ad esempio i dati di una richiesta Web o di un URL, gli input in controlli di un'applicazione Microsoft Windows Forms e così via, possono avere effetti negativi sul codice in quanto questi dati sono spesso utilizzati direttamente come parametri per chiamare altro codice.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-105">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="9c8ca-106">Questa situazione è analoga a quella della chiamata del codice da parte di codice dannoso con parametri insoliti ed è necessario adottare le stesse precauzioni.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-106">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="9c8ca-107">La sicurezza dell'input dell'utente è un'operazione difficile in quanto non è disponibile alcuno stack frame per registrare la presenza dei dati potenzialmente inattendibili.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-107">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>

<span data-ttu-id="9c8ca-108">Questi ultimi rappresentano i bug più difficili da rilevare in quanto, sebbene possano essere presenti in codice apparentemente non collegato alla sicurezza, costituiscono una porta tramite cui i dati dannosi possono essere passati ad altro codice.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-108">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="9c8ca-109">Per ricercare bug di questo tipo, prendere in considerazione i vari tipi di dati di input, immaginare l'intervallo dei valori possibili e determinare se il codice relativo a questi dati è in grado di gestire tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-109">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="9c8ca-110">Questi bug possono essere corretti tramite la verifica dell'intervallo e il rifiuto dell'input che non è possibile gestire tramite codice.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-110">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>

<span data-ttu-id="9c8ca-111">Tra gli aspetti importanti dei dati utente sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-111">Some important considerations involving user data include the following:</span></span>

- <span data-ttu-id="9c8ca-112">I dati utente in una risposta server sono eseguiti nel contesto del sito del server sul client.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-112">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="9c8ca-113">Se il server Web accetta i dati utente e li inserisce nella pagina \*\* \<\*\* Web restituita, potrebbe, ad esempio, includere uno script>tag ed essere eseguito come se provenivenga dal server.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-113">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>

- <span data-ttu-id="9c8ca-114">Tenere presente che il client può richiedere qualsiasi URL.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-114">Remember that the client can request any URL.</span></span>

- <span data-ttu-id="9c8ca-115">Prendere in considerazione i percorsi complessi o non validi:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-115">Consider tricky or invalid paths:</span></span>

  - <span data-ttu-id="9c8ca-116">..\ , percorsi estremamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-116">..\ , extremely long paths.</span></span>

  - <span data-ttu-id="9c8ca-117">Utilizzo di caratteri jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-117">Use of wild card characters (\*).</span></span>

  - <span data-ttu-id="9c8ca-118">Espansione del token (% token%).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-118">Token expansion (%token%).</span></span>

  - <span data-ttu-id="9c8ca-119">Forme insolite di percorsi con significati speciali.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-119">Strange forms of paths with special meaning.</span></span>

  - <span data-ttu-id="9c8ca-120">Nomi di flusso del file system alternativi come filename: `filename::$DATA`.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-120">Alternate file system stream names such as `filename::$DATA`.</span></span>

  - <span data-ttu-id="9c8ca-121">Versioni abbreviate dei nomi file come `longfi~1` per `longfilename`.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-121">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>

- <span data-ttu-id="9c8ca-122">Ricordare che Eval(userdata) consente di eseguire qualsiasi operazione.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-122">Remember that Eval(userdata) can do anything.</span></span>

- <span data-ttu-id="9c8ca-123">Tenere conto dell'associazione tardiva a un nome che include dati utente.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-123">Be wary of late binding to a name that includes some user data.</span></span>

- <span data-ttu-id="9c8ca-124">Se si utilizzano dati Web, prendere in considerazione le varie forme di escape consentite, inclusi:</span><span class="sxs-lookup"><span data-stu-id="9c8ca-124">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>

  - <span data-ttu-id="9c8ca-125">Escape esadecimali escape (%nn).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-125">Hexadecimal escapes (%nn).</span></span>

  - <span data-ttu-id="9c8ca-126">Escape Unicode (%nnn).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-126">Unicode escapes (%nnn).</span></span>

  - <span data-ttu-id="9c8ca-127">Escape lunghi UTF-8 (%nn%nn).</span><span class="sxs-lookup"><span data-stu-id="9c8ca-127">Overlong UTF-8 escapes (%nn%nn).</span></span>

  - <span data-ttu-id="9c8ca-128">Escape doppi (%nn diviene %mmnn, dove %mm è il carattere di escape per '%').</span><span class="sxs-lookup"><span data-stu-id="9c8ca-128">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>

- <span data-ttu-id="9c8ca-129">Prestare attenzione ai nomi utente che possono avere più di un formato canonico.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-129">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="9c8ca-130">Ad esempio, è spesso possibile utilizzare la forma MYDOMAIN\\*nomeutente* o la forma *nomeutente@mydomain.example.com*@mydomain.example.com.</span><span class="sxs-lookup"><span data-stu-id="9c8ca-130">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c8ca-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9c8ca-131">See also</span></span>

- [<span data-ttu-id="9c8ca-132">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="9c8ca-132">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
