---
title: 'Endpoint: errori di convalida e di autenticazione di sicurezza'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
author: BrucePerlerMS
ms.openlocfilehash: f7cd2268eefa0176ab71a3d5d3bc82c178664742
ms.sourcegitcommit: daa8788af67ac2d1cecd24f9f3409babb2f978c9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2018
ms.locfileid: "47862802"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="69c32-102">Endpoint: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="69c32-102">Endpoint: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="69c32-103">Nome contatore: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="69c32-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="69c32-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="69c32-104">Description</span></span>  
 <span data-ttu-id="69c32-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="69c32-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="69c32-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="69c32-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="69c32-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="69c32-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="69c32-108">Il client token non è stato autenticato (la password era errata).</span><span class="sxs-lookup"><span data-stu-id="69c32-108">Client token has failed authentication (bad password).</span></span>  
  
-   <span data-ttu-id="69c32-109">La verifica della firma non è riuscita (il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="69c32-109">Signature verification has failed (the message has been tampered).</span></span>  
  
-   <span data-ttu-id="69c32-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="69c32-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="69c32-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="69c32-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="69c32-112">Alcuni elementi obbligatori (un timestamp o un blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="69c32-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="69c32-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="69c32-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
