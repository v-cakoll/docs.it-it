---
title: Interpretazione della traccia di rete
description: Informazioni su come usare la traccia per acquisire le chiamate effettuate dall'applicazione a diversi membri della classe System.Net nel .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 7a17e4ba14d8c5fe136667c4eb5bc5b2fd7a8242
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502366"
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="1862a-103">Interpretazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="1862a-103">Interpreting Network Tracing</span></span>
<span data-ttu-id="1862a-104">Quando la traccia di rete è abilitata, può essere usata per acquisire le chiamate effettuate dall'applicazione a diversi membri della classe <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="1862a-104">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="1862a-105">L'output di queste chiamate può essere simile agli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1862a-105">The output from these calls may be similar to the following examples.</span></span>  
  
```output
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61
```  
  
 <span data-ttu-id="1862a-106">Nell'esempio precedente [588] è l'identificatore univoco del thread corrente.</span><span class="sxs-lookup"><span data-stu-id="1862a-106">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="1862a-107">(4357) e (4387) sono timestamp che indicano il numero di millisecondi trascorsi dall'avvio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1862a-107">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="1862a-108">I dati che seguono il timestamp mostrano l'applicazione in ingresso e in uscita verso e dal metodo **Socket.Send**.</span><span class="sxs-lookup"><span data-stu-id="1862a-108">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="1862a-109">L'identificatore univoco dell'oggetto che esegue il metodo **Send** è 33574638.</span><span class="sxs-lookup"><span data-stu-id="1862a-109">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="1862a-110">La traccia di uscita dal metodo include il valore restituito (61 nell'esempio precedente).</span><span class="sxs-lookup"><span data-stu-id="1862a-110">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="1862a-111">Le tracce di rete possono acquisire il traffico di rete inviato o ricevuto dall'applicazione usando protocolli a livello di applicazione come HTTP (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="1862a-111">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="1862a-112">Questi dati possono essere acquisiti come testo e, facoltativamente, come dati esadecimali.</span><span class="sxs-lookup"><span data-stu-id="1862a-112">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="1862a-113">I dati esadecimali sono disponibili quando si specifica **includehex** come valore dell'attributo **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="1862a-113">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="1862a-114">Per informazioni dettagliate su questo attributo, vedere [procedura: configurare la traccia di rete](how-to-configure-network-tracing.md). La traccia di esempio seguente è stata generata usando **includehex**.</span><span class="sxs-lookup"><span data-stu-id="1862a-114">(For detailed information about this attribute, see [How to: Configure Network Tracing](how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="1862a-115">Per omettere i dati esadecimali, specificare **protocolonly** come valore dell'attributo **tracemode**.</span><span class="sxs-lookup"><span data-stu-id="1862a-115">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="1862a-116">L'esempio seguente mostra la traccia quando è specificato **protocolonly**.</span><span class="sxs-lookup"><span data-stu-id="1862a-116">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="1862a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1862a-117">See also</span></span>

- [<span data-ttu-id="1862a-118">Abilitazione della traccia di rete</span><span class="sxs-lookup"><span data-stu-id="1862a-118">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="1862a-119">Procedura: Configurare la traccia di rete</span><span class="sxs-lookup"><span data-stu-id="1862a-119">How to: Configure Network Tracing</span></span>](how-to-configure-network-tracing.md)
- [<span data-ttu-id="1862a-120">Traccia di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1862a-120">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
