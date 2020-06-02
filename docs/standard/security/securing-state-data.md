---
title: Protezione dei dati di stato
description: Dichiarare i dati sullo stato come variabili private o interne per limitare l'accesso. È comunque possibile accedere a tali dati tramite reflection, serializzazione e durante il debug.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: b7fcb520fe6fa28cc098c4e1cbb56ce7da759c11
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291045"
---
# <a name="securing-state-data"></a><span data-ttu-id="c678f-104">Protezione dei dati di stato</span><span class="sxs-lookup"><span data-stu-id="c678f-104">Securing State Data</span></span>
<span data-ttu-id="c678f-105">Nelle applicazioni che consentono la gestione di dati sensibili o decisioni di qualsiasi tipo in materia di sicurezza è necessario mantenere il controllo dei dati e non consentire l'accesso diretto da parte di altro codice potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="c678f-105">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="c678f-106">Il modo migliore per proteggere i dati in memoria è dichiararli come variabili private o interne, ovvero con ambito limitato allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="c678f-106">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="c678f-107">Anche questi dati sono tuttavia soggetti a un tipo di accesso che è necessario determinare.</span><span class="sxs-lookup"><span data-stu-id="c678f-107">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="c678f-108">Tramite meccanismi di reflection, è possibile ottenere e impostare membri privati in codice altamente attendibile che può fare riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c678f-108">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="c678f-109">Tramite serializzazione, è possibile ottenere e impostare membri privati in codice altamente attendibile se è possibile accedere ai dati corrispondenti nella forma serializzata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c678f-109">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="c678f-110">Nella fase di debug, questi dati possono essere letti.</span><span class="sxs-lookup"><span data-stu-id="c678f-110">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="c678f-111">Accertarsi che nessun metodo o proprietà esponga tali valori in modo non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="c678f-111">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c678f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c678f-112">See also</span></span>

- [<span data-ttu-id="c678f-113">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="c678f-113">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)
