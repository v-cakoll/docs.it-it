---
title: Sicurezza e input dell'utente
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], user input
- user input, security
- secure coding, user input
- code security, user input
ms.assetid: 9141076a-96c9-4b01-93de-366bb1d858bc
ms.openlocfilehash: 0d34b06b44241feb7d6e3c8f76447b861563cfdc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705860"
---
# <a name="security-and-user-input"></a><span data-ttu-id="fd755-102">Sicurezza e input dell'utente</span><span class="sxs-lookup"><span data-stu-id="fd755-102">Security and User Input</span></span>

<span data-ttu-id="fd755-103">I dati utente, ovvero tutti i tipi di input, ad esempio i dati di una richiesta Web o di un URL, gli input in controlli di un'applicazione Microsoft Windows Forms e così via, possono avere effetti negativi sul codice in quanto questi dati sono spesso utilizzati direttamente come parametri per chiamare altro codice.</span><span class="sxs-lookup"><span data-stu-id="fd755-103">User data, which is any kind of input (data from a Web request or URL, input to controls of a Microsoft Windows Forms application, and so on), can adversely influence code because often that data is used directly as parameters to call other code.</span></span> <span data-ttu-id="fd755-104">Questa situazione è analoga a quella della chiamata del codice da parte di codice dannoso con parametri insoliti ed è necessario adottare le stesse precauzioni.</span><span class="sxs-lookup"><span data-stu-id="fd755-104">This situation is analogous to malicious code calling your code with strange parameters, and the same precautions should be taken.</span></span> <span data-ttu-id="fd755-105">La sicurezza dell'input dell'utente è un'operazione difficile in quanto non è disponibile alcuno stack frame per registrare la presenza dei dati potenzialmente inattendibili.</span><span class="sxs-lookup"><span data-stu-id="fd755-105">User input is actually harder to make safe because there is no stack frame to trace the presence of the potentially untrusted data.</span></span>

<span data-ttu-id="fd755-106">Questi ultimi rappresentano i bug più difficili da rilevare in quanto, sebbene possano essere presenti in codice apparentemente non collegato alla sicurezza, costituiscono una porta tramite cui i dati dannosi possono essere passati ad altro codice.</span><span class="sxs-lookup"><span data-stu-id="fd755-106">These are among the subtlest and hardest security bugs to find because, although they can exist in code that is seemingly unrelated to security, they are a gateway to pass bad data through to other code.</span></span> <span data-ttu-id="fd755-107">Per ricercare bug di questo tipo, prendere in considerazione i vari tipi di dati di input, immaginare l'intervallo dei valori possibili e determinare se il codice relativo a questi dati è in grado di gestire tutti i casi.</span><span class="sxs-lookup"><span data-stu-id="fd755-107">To look for these bugs, follow any kind of input data, imagine what the range of possible values might be, and consider whether the code seeing this data can handle all those cases.</span></span> <span data-ttu-id="fd755-108">Questi bug possono essere corretti tramite la verifica dell'intervallo e il rifiuto dell'input che non è possibile gestire tramite codice.</span><span class="sxs-lookup"><span data-stu-id="fd755-108">You can fix these bugs through range checking and rejecting any input the code cannot handle.</span></span>

<span data-ttu-id="fd755-109">Tra gli aspetti importanti dei dati utente sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd755-109">Some important considerations involving user data include the following:</span></span>

- <span data-ttu-id="fd755-110">I dati utente in una risposta server sono eseguiti nel contesto del sito del server sul client.</span><span class="sxs-lookup"><span data-stu-id="fd755-110">Any user data in a server response runs in the context of the server's site on the client.</span></span> <span data-ttu-id="fd755-111">Se il server Web accetta dati utente e li inserisce nella pagina Web restituita, può, ad esempio, includere un tag **\<script>** e consentire l'esecuzione come se questa avvenisse dal server.</span><span class="sxs-lookup"><span data-stu-id="fd755-111">If your Web server takes user data and inserts it into the returned Web page, it might, for example, include a **\<script>** tag and run as if from the server.</span></span>

- <span data-ttu-id="fd755-112">Tenere presente che il client può richiedere qualsiasi URL.</span><span class="sxs-lookup"><span data-stu-id="fd755-112">Remember that the client can request any URL.</span></span>

- <span data-ttu-id="fd755-113">Prendere in considerazione i percorsi complessi o non validi:</span><span class="sxs-lookup"><span data-stu-id="fd755-113">Consider tricky or invalid paths:</span></span>

  - <span data-ttu-id="fd755-114">..\ , percorsi estremamente lunghi.</span><span class="sxs-lookup"><span data-stu-id="fd755-114">..\ , extremely long paths.</span></span>

  - <span data-ttu-id="fd755-115">Utilizzo di caratteri jolly (\*).</span><span class="sxs-lookup"><span data-stu-id="fd755-115">Use of wild card characters (\*).</span></span>

  - <span data-ttu-id="fd755-116">Espansione del token (% token%).</span><span class="sxs-lookup"><span data-stu-id="fd755-116">Token expansion (%token%).</span></span>

  - <span data-ttu-id="fd755-117">Forme insolite di percorsi con significati speciali.</span><span class="sxs-lookup"><span data-stu-id="fd755-117">Strange forms of paths with special meaning.</span></span>

  - <span data-ttu-id="fd755-118">Nomi di flusso del file system alternativi come filename: `filename::$DATA`.</span><span class="sxs-lookup"><span data-stu-id="fd755-118">Alternate file system stream names such as `filename::$DATA`.</span></span>

  - <span data-ttu-id="fd755-119">Versioni abbreviate dei nomi file come `longfi~1` per `longfilename`.</span><span class="sxs-lookup"><span data-stu-id="fd755-119">Short versions of file names such as `longfi~1` for `longfilename`.</span></span>

- <span data-ttu-id="fd755-120">Ricordare che Eval(userdata) consente di eseguire qualsiasi operazione.</span><span class="sxs-lookup"><span data-stu-id="fd755-120">Remember that Eval(userdata) can do anything.</span></span>

- <span data-ttu-id="fd755-121">Tenere conto dell'associazione tardiva a un nome che include dati utente.</span><span class="sxs-lookup"><span data-stu-id="fd755-121">Be wary of late binding to a name that includes some user data.</span></span>

- <span data-ttu-id="fd755-122">Se si utilizzano dati Web, prendere in considerazione le varie forme di escape consentite, inclusi:</span><span class="sxs-lookup"><span data-stu-id="fd755-122">If you are dealing with Web data, consider the various forms of escapes that are permissible, including:</span></span>

  - <span data-ttu-id="fd755-123">Escape esadecimali escape (%nn).</span><span class="sxs-lookup"><span data-stu-id="fd755-123">Hexadecimal escapes (%nn).</span></span>

  - <span data-ttu-id="fd755-124">Escape Unicode (%nnn).</span><span class="sxs-lookup"><span data-stu-id="fd755-124">Unicode escapes (%nnn).</span></span>

  - <span data-ttu-id="fd755-125">Escape lunghi UTF-8 (%nn%nn).</span><span class="sxs-lookup"><span data-stu-id="fd755-125">Overlong UTF-8 escapes (%nn%nn).</span></span>

  - <span data-ttu-id="fd755-126">Escape doppi (%nn diviene %mmnn, dove %mm è il carattere di escape per '%').</span><span class="sxs-lookup"><span data-stu-id="fd755-126">Double escapes (%nn becomes %mmnn, where %mm is the escape for '%').</span></span>

- <span data-ttu-id="fd755-127">Prestare attenzione ai nomi utente che possono avere più di un formato canonico.</span><span class="sxs-lookup"><span data-stu-id="fd755-127">Be wary of user names that might have more than one canonical format.</span></span> <span data-ttu-id="fd755-128">Ad esempio, è spesso possibile utilizzare la forma MYDOMAIN\\*nomeutente* o la forma *nomeutente@mydomain.example.com*@mydomain.example.com.</span><span class="sxs-lookup"><span data-stu-id="fd755-128">For example, you can often use either the MYDOMAIN\\*username* form or the *username*@mydomain.example.com form.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd755-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd755-129">See also</span></span>

- [<span data-ttu-id="fd755-130">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="fd755-130">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
