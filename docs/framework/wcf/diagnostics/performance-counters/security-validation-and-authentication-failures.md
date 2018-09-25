---
title: Errori di convalida e di autenticazione della protezione
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
ms.openlocfilehash: d13e94800d71c6f567c6aab61974e42b1a3f1706
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070942"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="f10e9-102">Errori di convalida e di autenticazione della protezione</span><span class="sxs-lookup"><span data-stu-id="f10e9-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="f10e9-103">Nome contatore: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f10e9-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="f10e9-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f10e9-104">Description</span></span>  
 <span data-ttu-id="f10e9-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="f10e9-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="f10e9-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="f10e9-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="f10e9-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="f10e9-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="f10e9-108">Il client token non è stato autenticato (ad esempio la password era errata).</span><span class="sxs-lookup"><span data-stu-id="f10e9-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="f10e9-109">La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="f10e9-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="f10e9-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="f10e9-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="f10e9-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="f10e9-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="f10e9-112">Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="f10e9-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="f10e9-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="f10e9-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
