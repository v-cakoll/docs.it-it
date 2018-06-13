---
title: Errori di convalida e di autenticazione della protezione
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d7964c59f28f33d6ec7bc3ba605b84e6a201b14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474259"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="9d30a-102">Errori di convalida e di autenticazione della protezione</span><span class="sxs-lookup"><span data-stu-id="9d30a-102">Security Validation and Authentication Failures</span></span>
<span data-ttu-id="9d30a-103">Nome contatore: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="9d30a-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="9d30a-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d30a-104">Description</span></span>  
 <span data-ttu-id="9d30a-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="9d30a-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="9d30a-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="9d30a-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="9d30a-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d30a-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="9d30a-108">Il client token non è stato autenticato (ad esempio la password era errata).</span><span class="sxs-lookup"><span data-stu-id="9d30a-108">Client token has failed authentication (for example, bad password).</span></span>  
  
-   <span data-ttu-id="9d30a-109">La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="9d30a-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="9d30a-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="9d30a-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="9d30a-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="9d30a-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="9d30a-112">Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="9d30a-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="9d30a-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="9d30a-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
