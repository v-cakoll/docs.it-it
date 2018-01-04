---
title: Errori di convalida e di autenticazione della protezione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c52b54d2be2e824de478e0ee9ec2452c57e181b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="security-validation-and-authentication-failures"></a>Errori di convalida e di autenticazione della protezione
Nome contatore: errori di convalida e di autenticazione di sicurezza  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
-   Non è stato possibile leggere il token client dal messaggio.  
  
-   Il client token non è stato autenticato (ad esempio la password era errata).  
  
-   La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).  
  
-   Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
-   Si è verificato un errore di decrittografia.  
  
-   Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
-   Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.
