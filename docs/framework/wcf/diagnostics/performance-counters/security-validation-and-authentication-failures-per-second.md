---
title: Errori di convalida di sicurezza e di autenticazione al secondo
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: 546d81b73e912915d265fb194de4ad9e45d55cea
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163917"
---
# <a name="security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="6f250-102">Errori di convalida di sicurezza e di autenticazione al secondo</span><span class="sxs-lookup"><span data-stu-id="6f250-102">Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="6f250-103">Nome contatore: errori di convalida di sicurezza e di autenticazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="6f250-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6f250-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f250-104">Description</span></span>  
 <span data-ttu-id="6f250-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="6f250-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="6f250-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="6f250-106">Such problems include:</span></span>  
  
- <span data-ttu-id="6f250-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="6f250-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="6f250-108">Il client token non è stato autenticato (ad esempio la password era errata).</span><span class="sxs-lookup"><span data-stu-id="6f250-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="6f250-109">La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="6f250-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="6f250-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="6f250-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="6f250-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="6f250-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="6f250-112">Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="6f250-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="6f250-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="6f250-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="6f250-114">Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="6f250-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="6f250-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="6f250-115">(N1-N0)/((D1-D0)/F)</span></span>
