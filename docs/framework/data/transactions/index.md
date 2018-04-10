---
title: Elaborazione delle transazioni
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: effdc8e6-accf-41eb-98a5-431603ba218b
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6c66e982715d0f7f97e7a4faa92c2de57f3b1471
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-processing"></a><span data-ttu-id="ca26c-102">Elaborazione delle transazioni</span><span class="sxs-lookup"><span data-stu-id="ca26c-102">Transaction Processing</span></span>
<span data-ttu-id="ca26c-103">Quando si acquista un libro da una libreria online si offre denaro (tramite carta di credito) in cambio di un libro.</span><span class="sxs-lookup"><span data-stu-id="ca26c-103">When you purchase a book from an online bookstore, you exchange money (in the form of credit) for a book.</span></span> <span data-ttu-id="ca26c-104">Se la carta di credito è valida, una serie di operazioni correlate garantisce che l'acquirente riceva il libro e che la libreria riceva il denaro.</span><span class="sxs-lookup"><span data-stu-id="ca26c-104">If your credit is good, a series of related operations ensures that you get the book and the bookstore gets your money.</span></span> <span data-ttu-id="ca26c-105">Se tuttavia durante lo scambio si verifica un errore in una delle operazioni della serie, l'intero scambio ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="ca26c-105">However, if a single operation in the series fails during the exchange, the entire exchange fails.</span></span> <span data-ttu-id="ca26c-106">L'acquirente non riceve il libro e la libreria non riceve il denaro.</span><span class="sxs-lookup"><span data-stu-id="ca26c-106">You do not get the book and the bookstore does not get your money.</span></span>  
  
 <span data-ttu-id="ca26c-107">La tecnologia responsabile dell'equità e della prevedibilità dello scambio è detta elaborazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ca26c-107">The technology responsible for making the exchange balanced and predictable is called transaction processing.</span></span> <span data-ttu-id="ca26c-108">Le transazioni garantiscono che le risorse orientate ai dati vengano aggiornate in via definitiva solo dopo che tutte le operazioni all'interno dell'unità transazionale siano state completate correttamente.</span><span class="sxs-lookup"><span data-stu-id="ca26c-108">Transactions ensure that data-oriented resources are not permanently updated unless all operations within the transactional unit complete successfully.</span></span> <span data-ttu-id="ca26c-109">La combinazione di un set di operazioni correlate in un'unità in cui tutte le operazioni hanno lo stesso esito, sia esso positivo o negativo, consente di semplificare il ripristino in caso di errore e di rendere l'applicazione più affidabile.</span><span class="sxs-lookup"><span data-stu-id="ca26c-109">By combining a set of related operations into a unit that either completely succeeds or completely fails, you can simplify error recovery and make your application more reliable.</span></span>  
  
 <span data-ttu-id="ca26c-110">I sistemi di elaborazione delle transazioni si basano sull'hosting in componenti hardware e software di un'applicazione orientata alle transazioni che esegue le transazioni di routine necessarie allo svolgimento di attività aziendali.</span><span class="sxs-lookup"><span data-stu-id="ca26c-110">Transaction processing systems consist of computer hardware and software hosting a transaction-oriented application that performs the routine transactions necessary to conduct business.</span></span> <span data-ttu-id="ca26c-111">Alcuni esempi di tale applicazione sono i sistemi che gestiscono la registrazione degli ordini di vendita, la prenotazione di biglietti aerei, le retribuzioni, i record degli impiegati, la lavorazione e la spedizione di merci.</span><span class="sxs-lookup"><span data-stu-id="ca26c-111">Examples include systems that manage sales order entry, airline reservations, payroll, employee records, manufacturing, and shipping.</span></span>  
  
 <span data-ttu-id="ca26c-112">Questa sezione fornisce sia informazioni di carattere generale sull'elaborazione delle transazioni sia informazioni specifiche su come scrivere applicazioni transazionali e gestori di risorse tramite Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca26c-112">This section provides both general information on transaction processing, and specific information on how to write transactional applications and resource managers using the Microsoft .NET Framework.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca26c-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ca26c-113">In This Section</span></span>  
 [<span data-ttu-id="ca26c-114">Nozioni fondamentali sulle transazioni</span><span class="sxs-lookup"><span data-stu-id="ca26c-114">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 <span data-ttu-id="ca26c-115">Introduce i termini e in concetti fondamentali relativi all'elaborazione delle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ca26c-115">Introduces basic transaction processing terms and concepts.</span></span>  
  
 [<span data-ttu-id="ca26c-116">Funzionalità offerte da System.Transactions</span><span class="sxs-lookup"><span data-stu-id="ca26c-116">Features Provided by System.Transactions</span></span>](../../../../docs/framework/data/transactions/features-provided-by-system-transactions.md)  
 <span data-ttu-id="ca26c-117">Descrive come utilizzare le funzionalità di System.Transactions per scrivere un'applicazione transazionale personalizzata.</span><span class="sxs-lookup"><span data-stu-id="ca26c-117">Discusses how you can use features in System.Transactions to write your own transactional application.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ca26c-118">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="ca26c-118">Reference</span></span>  
 <xref:System.Transactions>  
 <span data-ttu-id="ca26c-119">Fornisce le classi che consentono al codice di partecipare alle transazioni.</span><span class="sxs-lookup"><span data-stu-id="ca26c-119">Provides classes that allow your code to participate in transactions.</span></span> <span data-ttu-id="ca26c-120">Tali classi supportano le transazioni con più partecipanti distribuiti, le notifiche a fase multipla e le integrazioni durevoli.</span><span class="sxs-lookup"><span data-stu-id="ca26c-120">The classes support transactions with multiple distributed participants, multiple phase notifications, and durable enlistments.</span></span>
