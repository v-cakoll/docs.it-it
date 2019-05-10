---
title: 'Servizio: Errori di convalida e di autenticazione della protezione'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: 5843d25eb26bdd9facc324a2af50c6b02c5ad7c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613589"
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="940a4-102">Servizio: Errori di convalida e di autenticazione della protezione</span><span class="sxs-lookup"><span data-stu-id="940a4-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="940a4-103">Nome contatore: Errori di convalida e di autenticazione della protezione</span><span class="sxs-lookup"><span data-stu-id="940a4-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="940a4-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="940a4-104">Description</span></span>  
 <span data-ttu-id="940a4-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="940a4-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="940a4-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="940a4-106">Such problems include:</span></span>  
  
- <span data-ttu-id="940a4-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="940a4-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="940a4-108">Il client token non è stato autenticato (ad esempio, la password era errata).</span><span class="sxs-lookup"><span data-stu-id="940a4-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
- <span data-ttu-id="940a4-109">La verifica della firma non è riuscita (ad esempio, il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="940a4-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
- <span data-ttu-id="940a4-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="940a4-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="940a4-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="940a4-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="940a4-112">Alcuni elementi obbligatori (ad esempio, timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="940a4-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="940a4-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="940a4-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
