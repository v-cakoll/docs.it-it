---
title: 'Servizio: errori di convalida di sicurezza e di autenticazione al secondo'
ms.date: 03/30/2017
ms.assetid: 4af18009-e778-490b-9ba6-e76485285830
ms.openlocfilehash: f3f27100afb7390a68d99421cad6f43d9abaccd5
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163865"
---
# <a name="service-security-validation-and-authentication-failures-per-second"></a>Servizio: errori di convalida di sicurezza e di autenticazione al secondo
Nome contatore: errori di convalida di sicurezza e di autenticazione al secondo.  
  
## <a name="description"></a>Descrizione  
 Questo contatore avanza ogni volta che un messaggio viene rifiutato a causa di un problema di sicurezza non coperto dal contatore "chiamate di sicurezza non autorizzate". Tra tali problemi si contano:  
  
- Non è stato possibile leggere il token client dal messaggio.  
  
- Il client token non è stato autenticato (ad esempio la password era errata).  
  
- La verifica della firma non è riuscita (ad esempio il messaggio è stato manomesso).  
  
- Il messaggio è un duplicato di un messaggio precedente. Ciò può verificarsi durante un attacco di tipo replay.  
  
- Si è verificato un errore di decrittografia.  
  
- Alcuni elementi obbligatori (ad esempio timestamp mancante o blocco di dati crittografati) non sono presenti nel messaggio.  
  
- Gli errori si sono verificati durante l'handshake TLSNEGO/SPNEGO.  
  
 Questo contatore è del tipo di contatore delle prestazioni [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), il cui valore viene calcolato utilizzando la formula seguente:  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
