---
title: Modelli di transazione
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 8731b72d0657aa420dbb020e216c3af059916ce9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517783"
---
# <a name="transaction-models"></a><span data-ttu-id="1a362-102">Modelli di transazione</span><span class="sxs-lookup"><span data-stu-id="1a362-102">Transaction Models</span></span>
<span data-ttu-id="1a362-103">In questo argomento viene descritta la relazione tra i modelli di programmazione della transazione e i componenti dell'infrastruttura forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a362-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="1a362-104">Quando si utilizzano transazioni in Windows Communication Foundation (WCF), è importante comprendere che sono non selezionando tra modelli transazionali differenti ma piuttosto operando a livelli differenti di un modello integrato e coerenza.</span><span class="sxs-lookup"><span data-stu-id="1a362-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="1a362-105">Nelle sezioni seguenti vengono descritti i tre componenti primari della transazione.</span><span class="sxs-lookup"><span data-stu-id="1a362-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="1a362-106">Transazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="1a362-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="1a362-107">Il supporto delle transazioni in WCF consente di che scrivere servizi transazionali.</span><span class="sxs-lookup"><span data-stu-id="1a362-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="1a362-108">Inoltre, grazie al supporto per il protocollo WS-AtomicTransaction (WS-AT), le applicazioni possono propagare transazioni a servizi Web generati tramite WCF o tecnologia di terze parti.</span><span class="sxs-lookup"><span data-stu-id="1a362-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="1a362-109">In un'applicazione o un servizio WCF, funzionalità di transazione WCF forniscono attributi e configurazione per specificare in modo dichiarativo come e quando l'infrastruttura deve creare, flusso e sincronizzare transazioni.</span><span class="sxs-lookup"><span data-stu-id="1a362-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="1a362-110">Transazioni System.Transactions</span><span class="sxs-lookup"><span data-stu-id="1a362-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="1a362-111">Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="1a362-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="1a362-112">Per altre informazioni su come creare un'applicazione transazionale utilizzando questi due modelli, vedere [scrittura di un'applicazione transazionale](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="1a362-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="1a362-113">In un servizio WCF o un'applicazione, <xref:System.Transactions> fornisce il modello di programmazione per la creazione di transazioni all'interno di un'applicazione client e per interagire in modo esplicito una transazione, quando necessario, all'interno di un servizio.</span><span class="sxs-lookup"><span data-stu-id="1a362-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="1a362-114">Transazioni MSDTC</span><span class="sxs-lookup"><span data-stu-id="1a362-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="1a362-115">MSDTC (Microsoft Distributed Transaction Coordinator) è un gestore transazioni che fornisce supporto per transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="1a362-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="1a362-116">Per altre informazioni, vedere la [di riferimento per programmatori di DTC](https://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="1a362-116">For more information, see the [DTC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="1a362-117">In un'applicazione o un servizio WCF, MSDTC fornisce l'infrastruttura per il coordinamento di transazioni create all'interno di un client o servizio.</span><span class="sxs-lookup"><span data-stu-id="1a362-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
