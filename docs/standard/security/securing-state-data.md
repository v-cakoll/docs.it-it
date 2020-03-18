---
title: Protezione dei dati di stato
description: Dichiarare i dati dello stato come variabili private o interne per limitare l'accesso ad esso. È comunque possibile accedere a tali dati tramite reflection, serializzazione e debug.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: f95bf409f7eef8c2636d3c180d2bbd95fbc689c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186816"
---
# <a name="securing-state-data"></a><span data-ttu-id="76954-104">Protezione dei dati di stato</span><span class="sxs-lookup"><span data-stu-id="76954-104">Securing State Data</span></span>
<span data-ttu-id="76954-105">Nelle applicazioni che consentono la gestione di dati sensibili o decisioni di qualsiasi tipo in materia di sicurezza è necessario mantenere il controllo dei dati e non consentire l'accesso diretto da parte di altro codice potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="76954-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="76954-106">Il modo migliore per proteggere i dati in memoria è dichiararli come variabili private o interne, ovvero con ambito limitato allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="76954-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="76954-107">Anche questi dati sono tuttavia soggetti a un tipo di accesso che è necessario determinare.</span><span class="sxs-lookup"><span data-stu-id="76954-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="76954-108">Tramite meccanismi di reflection, è possibile ottenere e impostare membri privati in codice altamente attendibile che può fare riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="76954-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="76954-109">Tramite serializzazione, è possibile ottenere e impostare membri privati in codice altamente attendibile se è possibile accedere ai dati corrispondenti nella forma serializzata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="76954-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="76954-110">Nella fase di debug, questi dati possono essere letti.</span><span class="sxs-lookup"><span data-stu-id="76954-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="76954-111">Accertarsi che nessun metodo o proprietà esponga tali valori in modo non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="76954-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76954-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76954-112">See also</span></span>

- [<span data-ttu-id="76954-113">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="76954-113">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
