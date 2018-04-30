---
title: Modelli di transazione
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c68a23e9ee86050a9db4c63c8c97d017794bce8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="transaction-models"></a><span data-ttu-id="7f5fa-102">Modelli di transazione</span><span class="sxs-lookup"><span data-stu-id="7f5fa-102">Transaction Models</span></span>
<span data-ttu-id="7f5fa-103">In questo argomento viene descritta la relazione tra i modelli di programmazione della transazione e i componenti dell'infrastruttura forniti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="7f5fa-104">Quando si utilizzano transazioni in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], è importante comprendere che non si sta selezionando tra modelli transazionali differenti ma piuttosto si sta operando a livelli differenti di un modello integrato e coerente.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="7f5fa-105">Nelle sezioni seguenti vengono descritti i tre componenti primari della transazione.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="7f5fa-106">Transazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="7f5fa-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="7f5fa-107">Il supporto delle transazioni in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] consente di scrivere servizi transazionali.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="7f5fa-108">Le applicazioni inoltre, con il supporto per il protocollo WS-AtomicTransaction (WS-AT), possono propagare transazioni a servizi Web generati tramite [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o tecnologia di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="7f5fa-109">In un servizio o in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], le funzionalità delle transazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forniscono attributi e configurazione per specificare in modo dichiarativo come e quando l'infrastruttura deve creare, propagare e sincronizzare transazioni.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="7f5fa-110">Transazioni System.Transactions</span><span class="sxs-lookup"><span data-stu-id="7f5fa-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="7f5fa-111">Lo spazio dei nomi <xref:System.Transactions> fornisce sia un modello di programmazione esplicito basato sulla classe <xref:System.Transactions.Transaction> sia un modello di programmazione implicito che utilizza la classe <xref:System.Transactions.TransactionScope>, in cui le transazioni vengono gestite automaticamente dall'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="7f5fa-112">Per ulteriori informazioni su come creare un'applicazione transazionale usando questi due modelli, vedere [scrittura di un'applicazione transazionale](http://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="7f5fa-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="7f5fa-113">In un servizio o in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], <xref:System.Transactions> fornisce il modello di programmazione per la creazione di transazioni all'interno di un'applicazione client e per l'interazione esplicita con una transazione, se necessario, all'interno di un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="7f5fa-114">Transazioni MSDTC</span><span class="sxs-lookup"><span data-stu-id="7f5fa-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="7f5fa-115">MSDTC (Microsoft Distributed Transaction Coordinator) è un gestore transazioni che fornisce supporto per transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="7f5fa-116">Per altre informazioni, vedere la [di riferimento per programmatori di DTC](http://go.microsoft.com/fwlink/?LinkId=94948).</span><span class="sxs-lookup"><span data-stu-id="7f5fa-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="7f5fa-117">In un servizio o in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], MSDTC fornisce l'infrastruttura per il coordinamento di transazioni create all'interno di un client o di un servizio.</span><span class="sxs-lookup"><span data-stu-id="7f5fa-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
