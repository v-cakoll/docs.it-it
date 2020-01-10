---
title: Protezione dei dati di stato
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
ms.openlocfilehash: c30bd2fe9e1ed371be2db60739d3b329fea788c7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705899"
---
# <a name="securing-state-data"></a><span data-ttu-id="e25d7-102">Protezione dei dati di stato</span><span class="sxs-lookup"><span data-stu-id="e25d7-102">Securing State Data</span></span>
<span data-ttu-id="e25d7-103">Nelle applicazioni che consentono la gestione di dati sensibili o decisioni di qualsiasi tipo in materia di sicurezza è necessario mantenere il controllo dei dati e non consentire l'accesso diretto da parte di altro codice potenzialmente dannoso.</span><span class="sxs-lookup"><span data-stu-id="e25d7-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="e25d7-104">Il modo migliore per proteggere i dati in memoria è dichiararli come variabili private o interne, ovvero con ambito limitato allo stesso assembly.</span><span class="sxs-lookup"><span data-stu-id="e25d7-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="e25d7-105">Anche questi dati sono tuttavia soggetti a un tipo di accesso che è necessario determinare.</span><span class="sxs-lookup"><span data-stu-id="e25d7-105">However, even this data is subject to access you should be aware of:</span></span>  
  
- <span data-ttu-id="e25d7-106">Tramite meccanismi di reflection, è possibile ottenere e impostare membri privati in codice altamente attendibile che può fare riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e25d7-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
- <span data-ttu-id="e25d7-107">Tramite serializzazione, è possibile ottenere e impostare membri privati in codice altamente attendibile se è possibile accedere ai dati corrispondenti nella forma serializzata dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e25d7-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
- <span data-ttu-id="e25d7-108">Nella fase di debug, questi dati possono essere letti.</span><span class="sxs-lookup"><span data-stu-id="e25d7-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="e25d7-109">Accertarsi che nessun metodo o proprietà esponga tali valori in modo non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="e25d7-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25d7-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e25d7-110">See also</span></span>

- [<span data-ttu-id="e25d7-111">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="e25d7-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
