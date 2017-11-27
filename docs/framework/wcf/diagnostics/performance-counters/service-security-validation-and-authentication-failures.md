---
title: 'Servizio: errori di convalida e di autenticazione di sicurezza'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 808c0d648043df6c5a3dda4646e45ba1492345a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="service-security-validation-and-authentication-failures"></a><span data-ttu-id="87755-102">Servizio: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="87755-102">Service: Security Validation and Authentication Failures</span></span>
<span data-ttu-id="87755-103">Nome contatore: errori di convalida e di autenticazione di sicurezza</span><span class="sxs-lookup"><span data-stu-id="87755-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="87755-104">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87755-104">Description</span></span>  
 <span data-ttu-id="87755-105">Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate".</span><span class="sxs-lookup"><span data-stu-id="87755-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="87755-106">Tra tali problemi si contano:</span><span class="sxs-lookup"><span data-stu-id="87755-106">Such problems include:</span></span>  
  
-   <span data-ttu-id="87755-107">Non è stato possibile leggere il token client dal messaggio.</span><span class="sxs-lookup"><span data-stu-id="87755-107">Client token cannot be read from the message.</span></span>  
  
-   <span data-ttu-id="87755-108">Il client token non è stato autenticato (ad esempio, la password era errata).</span><span class="sxs-lookup"><span data-stu-id="87755-108">Client token has failed authentication (for example,, bad password).</span></span>  
  
-   <span data-ttu-id="87755-109">La verifica della firma non è riuscita (ad esempio, il messaggio è stato manomesso).</span><span class="sxs-lookup"><span data-stu-id="87755-109">Signature verification has failed (for example,, the message has been tampered).</span></span>  
  
-   <span data-ttu-id="87755-110">Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.</span><span class="sxs-lookup"><span data-stu-id="87755-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
-   <span data-ttu-id="87755-111">Si è verificato un errore di decrittografia.</span><span class="sxs-lookup"><span data-stu-id="87755-111">A decryption failure has occurred.</span></span>  
  
-   <span data-ttu-id="87755-112">Alcuni elementi obbligatori (ad esempio, timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="87755-112">Some required elements (for example,, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
-   <span data-ttu-id="87755-113">Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="87755-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
