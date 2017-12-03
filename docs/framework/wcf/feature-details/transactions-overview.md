---
title: Panoramica sulle transazioni di Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 480c7ca971eeb7f232517057efe4033f177b26b3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="windows-communication-foundation-transactions-overview"></a><span data-ttu-id="52a69-102">Panoramica sulle transazioni di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="52a69-102">Windows Communication Foundation Transactions Overview</span></span>
<span data-ttu-id="52a69-103">Le transazioni consentono di radunare un set di azioni o operazioni in un'unica unità di esecuzione indivisibile.</span><span class="sxs-lookup"><span data-stu-id="52a69-103">Transactions provide a way to group a set of actions or operations into a single indivisible unit of execution.</span></span> <span data-ttu-id="52a69-104">Una transazione è una raccolta di operazioni con le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="52a69-104">A transaction is a collection of operations with the following properties:</span></span>  
  
-   <span data-ttu-id="52a69-105">Atomicità.</span><span class="sxs-lookup"><span data-stu-id="52a69-105">Atomicity.</span></span> <span data-ttu-id="52a69-106">Questo aspetto assicura che tutti gli aggiornamenti completati in una transazione specifica vengano sottoposti a commit e resi durevoli oppure vengono tutti interrotti e sottoposti a rollback allo stato precedente.</span><span class="sxs-lookup"><span data-stu-id="52a69-106">This ensures that either all of the updates completed under a specific transaction are committed and made durable or they are all aborted and rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="52a69-107">Coerenza.</span><span class="sxs-lookup"><span data-stu-id="52a69-107">Consistency.</span></span> <span data-ttu-id="52a69-108">Questa caratteristica garantisce che le modifiche eseguita in una transazione rappresentano una trasformazione da uno stato coerente a un altro.</span><span class="sxs-lookup"><span data-stu-id="52a69-108">This guarantees that the changes made under a transaction represent a transformation from one consistent state to another.</span></span> <span data-ttu-id="52a69-109">Ad esempio, una transazione che trasferisce denaro da un conto corrente a un conto di risparmio non modifica il quantità di denaro nel conto generale.</span><span class="sxs-lookup"><span data-stu-id="52a69-109">For example, a transaction that transfers money from a checking account to a savings account does not change the amount of money in the overall bank account.</span></span>  
  
-   <span data-ttu-id="52a69-110">Isolamento.</span><span class="sxs-lookup"><span data-stu-id="52a69-110">Isolation.</span></span> <span data-ttu-id="52a69-111">Questo aspetto impedisce a una transazione di applicare modifiche di cui non è stato eseguito il commit ad altre transazioni simultanee.</span><span class="sxs-lookup"><span data-stu-id="52a69-111">This prevents a transaction from observing uncommitted changes belonging to other concurrent transactions.</span></span> <span data-ttu-id="52a69-112">L'isolamento garantisce l'astrazione della concorrenza mentre assicura che una transazione non abbia un impatto imprevisto sull'esecuzione di un'altra transazione.</span><span class="sxs-lookup"><span data-stu-id="52a69-112">Isolation provides an abstraction of concurrency while ensuring one transaction cannot have an unexpected impact on the execution of another transaction.</span></span>  
  
-   <span data-ttu-id="52a69-113">Durabilità.</span><span class="sxs-lookup"><span data-stu-id="52a69-113">Durability.</span></span> <span data-ttu-id="52a69-114">Implica che, quando è stato eseguito il commit, gli aggiornamenti alle risorse gestite (ad esempio un record di database) verranno resi persistenti rispetto agli errori.</span><span class="sxs-lookup"><span data-stu-id="52a69-114">This means that once committed, updates to managed resources (such as a database record) will be persistent in the face of failures.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="52a69-115"> fornisce un vasta gamma di funzionalità che consentono di creare transazioni distribuite nell'applicazione di servizio Web.</span><span class="sxs-lookup"><span data-stu-id="52a69-115"> provides a rich set of features that enable you to create distributed transactions in your Web service application.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="52a69-116"> implementa il supporto per il protocollo WS-AtomicTransaction (WS-AT) che consente alle applicazioni [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] di propagare transazioni alle applicazioni interoperative, ad esempio i servizi Web interoperativi creati usando tecnologia di terze parti.</span><span class="sxs-lookup"><span data-stu-id="52a69-116"> implements support for the WS-AtomicTransaction (WS-AT) protocol that enables [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to flow transactions to interoperable applications, such as interoperable Web services built using third-party technology.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="52a69-117"> implementa anche il supporto per il protocollo delle transazioni OLE che può essere usato negli scenari in cui non è necessaria la funzionalità di interoperabilità per abilitare il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="52a69-117"> also implements support for the OLE Transactions protocol, which can be used in scenarios where you do not need interop functionality to enable transaction flow.</span></span>  
  
 <span data-ttu-id="52a69-118">È possibile usare un file di configurazione dell'applicazione per configurare associazioni che abilitano o disabilitano il flusso delle transazioni, nonché impostare il protocollo delle transazioni desiderato su un'associazione.</span><span class="sxs-lookup"><span data-stu-id="52a69-118">You can use an application configuration file to configure bindings to enable or disable transaction flow, as well as set the desired transaction protocol on a binding.</span></span> <span data-ttu-id="52a69-119">È inoltre possibile impostare timeout delle transazioni a livello di servizio usando il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="52a69-119">In addition, you can set transaction time-outs at the service level using the configuration file.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="52a69-120">[Attivazione del flusso di transazione](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="52a69-120"> [Enabling Transaction Flow](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
 <span data-ttu-id="52a69-121">Gli attributi delle transazioni nello spazio dei nomi <xref:System.ServiceModel> consentono di eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52a69-121">Transaction attributes in the <xref:System.ServiceModel> namespace allow you to do the following:</span></span>  
  
-   <span data-ttu-id="52a69-122">Configurare timeout delle transazioni e filtri a livello di isolamento usando l'attributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52a69-122">Configure transaction time-outs and isolation-level filtering using the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="52a69-123">Abilitare la funzionalità delle transazioni e configurare il comportamento di completamento delle transazioni usando l'attributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52a69-123">Enable transactions functionality and configure transaction completion behavior using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="52a69-124">Usare gli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> su un metodo del contratto per richiedere, consentire o negare il flusso delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="52a69-124">Use the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes on a contract method to require, allow or deny transaction flow.</span></span>  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="52a69-125">[Gli attributi della transazione di ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="52a69-125"> [ServiceModel Transaction Attributes](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a69-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52a69-126">See Also</span></span>  
 [<span data-ttu-id="52a69-127">Attributi della transazione di ServiceModel</span><span class="sxs-lookup"><span data-stu-id="52a69-127">ServiceModel Transaction Attributes</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [<span data-ttu-id="52a69-128">Attivazione del flusso delle transazioni</span><span class="sxs-lookup"><span data-stu-id="52a69-128">Enabling Transaction Flow</span></span>](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
