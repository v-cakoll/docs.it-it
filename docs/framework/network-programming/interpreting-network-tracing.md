---
title: Interpretazione della traccia di rete
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: fd617e152b1e86cc71dd8e3cc8a01f1d2f52c30a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047895"
---
# <a name="interpreting-network-tracing"></a>Interpretazione della traccia di rete
Quando la traccia di rete è abilitata, può essere usata per acquisire le chiamate effettuate dall'applicazione a diversi membri della classe <xref:System.Net>. L'output di queste chiamate può essere simile agli esempi seguenti.  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 Nell'esempio precedente [588] è l'identificatore univoco del thread corrente. (4357) e (4387) sono timestamp che indicano il numero di millisecondi trascorsi dall'avvio dell'applicazione. I dati che seguono il timestamp mostrano l'applicazione in ingresso e in uscita verso e dal metodo **Socket.Send**. L'identificatore univoco dell'oggetto che esegue il metodo **Send** è 33574638. La traccia di uscita dal metodo include il valore restituito (61 nell'esempio precedente).  
  
 Le tracce di rete possono acquisire il traffico di rete inviato o ricevuto dall'applicazione usando protocolli a livello di applicazione come HTTP (Hypertext Transfer Protocol). Questi dati possono essere acquisiti come testo e, facoltativamente, come dati esadecimali. I dati esadecimali sono disponibili quando si specifica **includehex** come valore dell'attributo **tracemode**. Per informazioni dettagliate su questo attributo, vedere [Procedura: configurare la traccia](how-to-configure-network-tracing.md)di rete. La traccia di esempio seguente è stata generata utilizzando **includehex**.  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 Per omettere i dati esadecimali, specificare **protocolonly** come valore dell'attributo **tracemode**. L'esempio seguente mostra la traccia quando è specificato **protocolonly**.  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a>Vedere anche

- [Abilitazione della traccia di rete](enabling-network-tracing.md)
- [Procedura: Configurare la traccia di rete](how-to-configure-network-tracing.md)
- [Traccia di rete in .NET Framework](network-tracing.md)
