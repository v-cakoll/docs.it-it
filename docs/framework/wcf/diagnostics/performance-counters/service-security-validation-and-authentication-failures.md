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
# <a name="service-security-validation-and-authentication-failures"></a>Servizio: errori di convalida e di autenticazione di sicurezza
Nome contatore: errori di convalida e di autenticazione di sicurezza  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
-   Non è stato possibile leggere il token client dal messaggio.  
  
-   Il client token non è stato autenticato (ad esempio, la password era errata).  
  
-   La verifica della firma non è riuscita (ad esempio, il messaggio è stato manomesso).  
  
-   Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
-   Si è verificato un errore di decrittografia.  
  
-   Alcuni elementi obbligatori (ad esempio, timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
-   Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.
