---
title: 'Servizio: errori di convalida di sicurezza e di autenticazione al secondo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 007bc3b38ef5b635a85e4c13f9bc9a6424fc36ad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a><span data-ttu-id="b2e65-102">Servizio: errori di convalida di sicurezza e di autenticazione al secondo</span><span class="sxs-lookup"><span data-stu-id="b2e65-102">Service: Security Validation and Authentication Failures Per Second</span></span>
<span data-ttu-id="b2e65-103">Nome contatore: errori di convalida di sicurezza e di autenticazione al secondo.</span><span class="sxs-lookup"><span data-stu-id="b2e65-103">Counter name: Security Validation and Authentication Failures Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b2e65-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b2e65-104">Description</span></span>  
 <span data-ttu-id="b2e65-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="b2e65-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="b2e65-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="b2e65-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="b2e65-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="b2e65-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="b2e65-108">Il client token non è stato autenticato (ad esempio la password era errata).</span><span class="sxs-lookup"><span data-stu-id="b2e65-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="b2e65-109">La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="b2e65-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="b2e65-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="b2e65-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="b2e65-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="b2e65-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="b2e65-112">Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="b2e65-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="b2e65-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="b2e65-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="b2e65-114">Questo contatore è di tipo di contatore prestazioni [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato usando la formula seguente,</span><span class="sxs-lookup"><span data-stu-id="b2e65-114">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula,</span></span>  
  
 <span data-ttu-id="b2e65-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b2e65-115">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
