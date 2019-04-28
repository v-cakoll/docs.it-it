---
title: 'Endpoint: Errori di convalida di sicurezza e di autenticazione al secondo'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 43886f79585fb9a63eeb51360cc869365c100a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916539"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="fdd57-102">Endpoint: Errori di convalida di sicurezza e di autenticazione al secondo</span><span class="sxs-lookup"><span data-stu-id="fdd57-102">Endpoint: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="fdd57-103">Nome contatore: Errori di convalida di sicurezza e di autenticazione al secondo</span><span class="sxs-lookup"><span data-stu-id="fdd57-103">Counter name: Security Validation and Authentication Failures Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="fdd57-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fdd57-104">Description</span></span>  
 <span data-ttu-id="fdd57-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="fdd57-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="fdd57-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="fdd57-106">Such problems include:</span></span>  
  
- <span data-ttu-id="fdd57-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="fdd57-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="fdd57-108">Il client token non è stato autenticato (ad esempio la password era errata).</span><span class="sxs-lookup"><span data-stu-id="fdd57-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="fdd57-109">La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="fdd57-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="fdd57-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="fdd57-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="fdd57-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="fdd57-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="fdd57-112">Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="fdd57-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="fdd57-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="fdd57-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="fdd57-114">Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente:</span><span class="sxs-lookup"><span data-stu-id="fdd57-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula:</span></span>  
  
 <span data-ttu-id="fdd57-115">(N1-N0)/((D1-D0)/F)</span><span class="sxs-lookup"><span data-stu-id="fdd57-115">(N1-N0)/((D1-D0)/F)</span></span>
