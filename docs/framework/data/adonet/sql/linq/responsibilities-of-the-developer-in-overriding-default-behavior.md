---
title: Responsabilità dello sviluppatore nell'override del comportamento predefinito
ms.date: 03/30/2017
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
ms.openlocfilehash: 90b8eedcc80c330a39efe97b6427beebeca913f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Responsabilità dello sviluppatore nell'override del comportamento predefinito
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non impone i requisiti seguenti, tuttavia il comportamento sarà indefinito se tali requisiti non vengono soddisfatti.  
  
-   Il metodo di override non deve chiamare <xref:System.Data.Linq.DataContext.SubmitChanges%2A> o <xref:System.Data.Linq.Table%601.Attach%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera un'eccezione se questi metodi vengono chiamati in un metodo di override.  
  
-   Non è possibile usare i metodi di override per avviare, eseguire il commit o interrompere una transazione. L'operazione <xref:System.Data.Linq.DataContext.SubmitChanges%2A> viene eseguita in una transazione. Una transazione annidata interna può interferire con la transazione esterna. I metodi di override del caricamento possono avviare una transazione solo dopo avere determinano che l'operazione non viene eseguita in <xref:System.Transactions.Transaction>.  
  
-   È previsto che i metodi di override seguano il mapping di concorrenza ottimistica applicabile. Il metodo di override dovrebbe generare un'eccezione <xref:System.Data.Linq.ChangeConflictException> quando si verifica un conflitto di concorrenza ottimistica. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] rileva questa eccezione in modo che è possibile elaborare correttamente le <xref:System.Data.Linq.DataContext.SubmitChanges%2A> opzione disponibile in <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   I metodi di creazione (`Insert`) e di override `Update` dovrebbero trasferire di nuovo i valori per le colonne generate dal database ai corrispondenti membri dell'oggetto quando l'operazione viene completata correttamente.  
  
     Ad esempio, se `Order.OrderID` viene eseguito il mapping a una colonna identity (*autoincrement* chiave primaria), quindi il `InsertOrder()` metodo di override deve recuperare l'ID generato dal database e impostare il `Order.OrderID` membro da tale ID. In modo analogo i membri del timestamp dovranno essere aggiornati in base ai valori di timestamp generati dal database per assicurarsi che gli oggetti aggiornati sono coerenti. La mancata propagazione dei valori generati dal database potrebbe comportare un'incoerenza tra il database e gli oggetti registrati da <xref:System.Data.Linq.DataContext>.  
  
-   È compito dell'utente richiamare l'API dinamica corretta. Ad esempio, nel metodo di override dell'aggiornamento è possibile chiamare solo <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] non rileva né verifica se il metodo dinamico richiamato corrisponde all'operazione applicabile. Se viene chiamato un metodo non applicabile, ad esempio <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> per un oggetto da aggiornare, i risultati sono indefiniti.  
  
-   Infine, il metodo di override dovrebbe eseguire l'operazione specificata. La semantica di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] operazioni, ad esempio il caricamento posticipato durante il caricamento, e <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) richiedono le sostituzioni per fornire il servizio specificato. Ad esempio, un override di caricamento che restituisce solo una raccolta vuota, senza controllare il contenuto nel database, causerà probabilmente la restituzione di dati incoerenti.  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
