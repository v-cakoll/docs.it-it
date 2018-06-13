---
title: 'Servizio: errori di convalida e di autenticazione di sicurezza'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e160b014b7aa7586566073b800084d44be15ccaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474402"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="f3052-102">Servizio: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3052-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="f3052-103">Nome contatore: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f3052-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="f3052-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3052-104">Description</span></span>  
 <span data-ttu-id="f3052-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="f3052-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="f3052-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="f3052-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="f3052-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3052-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="f3052-108">Il client token non è stato autenticato (ad esempio, la password era errata).</span><span class="sxs-lookup"><span data-stu-id="f3052-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="f3052-109">La verifica della firma non è riuscita (ad esempio, il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="f3052-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="f3052-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="f3052-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="f3052-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="f3052-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="f3052-112">Alcuni elementi obbligatori (ad esempio, timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="f3052-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="f3052-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="f3052-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
