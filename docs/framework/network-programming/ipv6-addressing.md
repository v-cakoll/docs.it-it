---
title: Indirizzamento IPv6
description: Informazioni sugli indirizzi IPv6 (Internet Protocol Version 6), inclusi la rappresentazione testuale e i tipi di indirizzo.
ms.date: 03/30/2017
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
ms.openlocfilehash: fbf68cb5f40450c2f9ecf4900801ee55e326fcb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502340"
---
# <a name="ipv6-addressing"></a>Indirizzamento IPv6

La lunghezza degli indirizzi IPv6 (Internet Protocol version 6) è di 128 bit. Uno dei motivi di uno spazio indirizzi così grande è la possibilità di suddividere gli indirizzi disponibili in una gerarchia di domini di routing che riflettono la topologia di Internet. Un altro motivo è poter eseguire il mapping degli indirizzi delle schede (o interfacce) di rete che connettono i dispositivi alla rete. IPv6 è automaticamente in grado di risolvere gli indirizzi al livello inferiore, ovvero a livello di interfaccia di rete, e include anche funzionalità di configurazione automatica.

## <a name="text-representation"></a>Rappresentazione di testo

Di seguito vengono mostrati tre formati convenzionali usati per rappresentare gli indirizzi IPv6 come stringhe di testo:

- **Formato con valori esadecimali separati da due punti**. Questo è il formato preferito: n:n:n:n:n:n:n:n. Ogni n rappresenta il valore esadecimale di uno degli otto elementi a 16 bit dell'indirizzo. Ad esempio: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.

- **Formato compresso**. A causa della lunghezza degli indirizzi, alcuni indirizzi contengono una lunga stringa di zeri. Per semplificare la scrittura di questi indirizzi, usare il formato compresso, in cui una singola sequenza contigua di blocchi di zeri viene rappresentata da un simbolo costituito da un doppio carattere di due punti (::). Questo simbolo può apparire una sola volta in un indirizzo. Ad esempio, l'indirizzo multicast `FFED:0:0:0:0:BA98:3210:4562` in formato compresso è `FFED::BA98:3210:4562`. L'indirizzo unicast `3FFE:FFFF:0:0:8:800:20C4:0` in formato compresso è `3FFE:FFFF::8:800:20C4:0`. L'indirizzo di loopback `0:0:0:0:0:0:0:1` in formato compresso è `::`1. L'indirizzo non specificato `0:0:0:0:0:0:0:0` in formato compresso è `::`.

- **Formato misto**. Questo formato combina indirizzi IPv4 e IPv6. In questo caso, il formato dell'indirizzo è n:n:n:n:n:n:d.d.d.d, dove ogni n rappresenta i valori esadecimali dei sei elementi a 16 bit significativi dell'indirizzo IPv6 e ogni d rappresenta il valore decimale di un indirizzo IPv4.

## <a name="address-types"></a>Tipo di indirizzo

I bit iniziali nell'indirizzo definiscono il tipo di indirizzo IPv6 specifico. Il campo a lunghezza variabile contenente questi bit iniziali è chiamato prefisso di formato.

Un indirizzo unicast IPv6 è diviso in due parti. La prima parte contiene il prefisso dell'indirizzo, mentre la seconda contiene l'identificatore di interfaccia. Un modo conciso per esprimere una combinazione indirizzo/prefisso IPv6 è: indirizzo-ipv6/lunghezza-prefisso.

L'esempio seguente mostra un indirizzo con prefisso a 64 bit.

`3FFE:FFFF:0:CD30:0:0:0:0/64`.

In questo esempio il prefisso è `3FFE:FFFF:0:CD30`. L'indirizzo può anche essere scritto in formato compresso, come `3FFE:FFFF:0:CD30::/64`.

IPv6 definisce i tipi di indirizzo seguenti:

- **Indirizzo unicast**. Identificatore per una singola interfaccia. Un pacchetto inviato a questo indirizzo viene recapitato all'interfaccia identificata. Gli indirizzi unicast si distinguono dagli indirizzi multicast per il valore dell'ottetto significativo. L'ottetto significativo degli indirizzi multicast ha il valore esadecimale FF. Qualsiasi altro valore per l'ottetto identifica un indirizzo unicast. Ecco alcuni tipi diversi di indirizzi unicast:

  - **Indirizzi locali rispetto al collegamento**. Questi indirizzi vengono usati in un singolo collegamento e hanno questo formato: FE80::*IDInterfaccia*. Gli indirizzi locali rispetto al collegamento vengono usati tra nodi in un collegamento per la configurazione automatica degli indirizzi, l'individuazione di router adiacenti o quando non è presente alcun router. Un indirizzo locale rispetto al collegamento viene usato in particolare all'avvio e quando il sistema non ha ancora acquisito indirizzi di ambito maggiore.

  - **Indirizzi locali rispetto al sito**. Questi indirizzi vengono usati in un singolo sito e hanno questo formato: FEC0::*IDSubnet*:*IDInterfaccia*. Gli indirizzi locali rispetto al sito vengono usati per l'indirizzamento all'interno di un sito senza necessità di un prefisso globale.

  - **Indirizzi unicast IPv6 globali**. Questi indirizzi possono essere usati in Internet e hanno questo formato: 010(PF, 3 bit) ID TLA (13 bit) bit riservati (8 bit) ID NLA (24 bit) ID SLA (16 bit) *InterfacciaID* (64 bit).

- **Indirizzo multicast**. Identificatore per un set di interfacce, in genere appartenenti a nodi diversi. Un pacchetto inviato a questo indirizzo viene recapitato a tutte le interfacce identificate dall'indirizzo. I tipi di indirizzo multicast sostituiscono gli indirizzi di broadcast IPv4.

- **Indirizzo anycast**. Identificatore per un set di interfacce, in genere appartenenti a nodi diversi. Un pacchetto inviato a questo indirizzo viene recapitato a una sola interfaccia identificata dall'indirizzo. Si tratta dell'interfaccia più vicina in base a quanto identificato dalle metriche di routing. Gli indirizzi anycast provengono dallo spazio indirizzi unicast e non sono distinguibili sintatticamente. L'interfaccia di destinazione esegue la distinzione tra indirizzi unicast e anycast come funzione della propria configurazione.

In generale, un nodo ha sempre un indirizzo locale rispetto al collegamento. Può avere anche un indirizzo locale rispetto al sito e uno o più indirizzi globali.

## <a name="see-also"></a>Vedere anche

- [Protocollo IP versione 6](internet-protocol-version-6.md)
- [Socket](sockets.md)
