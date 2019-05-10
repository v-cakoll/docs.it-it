---
title: Errori di convalida e di autenticazione della protezione
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 0f061e1e12321dbe8034d7619830f71717ca9d1f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664982"
---
# <a name="security-validation-and-authentication-failures"></a>Errori di convalida e di autenticazione della protezione
Nome contatore: Errori di convalida e di autenticazione della protezione  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
- Non è stato possibile leggere il token client dal messaggio.  
  
- Il client token non è stato autenticato (ad esempio la password era errata).  
  
- La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).  
  
- Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
- Si è verificato un errore di decrittografia.  
  
- Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
- Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.
