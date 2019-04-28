---
title: Errori di convalida di sicurezza e di autenticazione al secondo
ms.date: 03/30/2017
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
ms.openlocfilehash: e3db8cb20399bdff9b73a428ea2a53909da4eee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915772"
---
# <a name="security-validation-and-authentication-failures-per-second"></a>Errori di convalida di sicurezza e di autenticazione al secondo
Nome contatore: Convalida della sicurezza e gli errori di autenticazione al secondo.  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
- Non è stato possibile leggere il token client dal messaggio.  
  
- Il client token non è stato autenticato (ad esempio la password era errata).  
  
- La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).  
  
- Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
- Si è verificato un errore di decrittografia.  
  
- Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
- Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.  
  
 Questo contatore è di tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), il cui valore viene calcolato utilizzando la formula seguente:  
  
 (N1-N0)/((D1-D0)/F)
