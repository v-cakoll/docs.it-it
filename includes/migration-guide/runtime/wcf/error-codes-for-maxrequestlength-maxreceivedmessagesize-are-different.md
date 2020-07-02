---
ms.openlocfilehash: 3aafb14b65f7c0f9e5d77927809547f9d4b96e1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620371"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="f4e67-101">I codici di errore per maxRequestLength o maxReceivedMessageSize sono diversi</span><span class="sxs-lookup"><span data-stu-id="f4e67-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="f4e67-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="f4e67-102">Details</span></span>

<span data-ttu-id="f4e67-103">I messaggi nei servizi Web WCF ospitati in Internet Information Services (IIS) o ASP.NET Development Server che superano maxRequestLength (in ASP.NET) o maxReceivedMessageSize (in WCF) hanno un codice di errore diverso. Il codice di stato HTTP è cambiato da 400 (Richiesta non valida) a 413 (Entità troppo grande) e i messaggi che superano la soglia impostata da maxRequestLength o da maxReceivedMessageSize generano un'eccezione <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f4e67-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="f4e67-104">Sono inclusi i casi in cui la modalità di trasferimento è Streamed.</span><span class="sxs-lookup"><span data-stu-id="f4e67-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f4e67-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="f4e67-105">Suggestion</span></span>

<span data-ttu-id="f4e67-106">Questa modifica semplifica il debug nei casi in cui la lunghezza del messaggio supera i limiti consentiti da ASP.NET o WCF. È necessario modificare qualsiasi codice che esegue l'elaborazione in base a un codice di stato HTTP 400.</span><span class="sxs-lookup"><span data-stu-id="f4e67-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="f4e67-107">Nome</span><span class="sxs-lookup"><span data-stu-id="f4e67-107">Name</span></span>    | <span data-ttu-id="f4e67-108">Valore</span><span class="sxs-lookup"><span data-stu-id="f4e67-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f4e67-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f4e67-109">Scope</span></span>   |<span data-ttu-id="f4e67-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f4e67-110">Edge</span></span>|
|<span data-ttu-id="f4e67-111">Version</span><span class="sxs-lookup"><span data-stu-id="f4e67-111">Version</span></span>|<span data-ttu-id="f4e67-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f4e67-112">4.5</span></span>|
|<span data-ttu-id="f4e67-113">Type</span><span class="sxs-lookup"><span data-stu-id="f4e67-113">Type</span></span>|<span data-ttu-id="f4e67-114">Runtime</span><span class="sxs-lookup"><span data-stu-id="f4e67-114">Runtime</span></span>|
