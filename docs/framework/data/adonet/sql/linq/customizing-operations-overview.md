---
title: 'Personalizzazione di operazioni: panoramica'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7653ca137c93da5174e0ddcd1ced8bdfceaa9edc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="customizing-operations-overview"></a>Personalizzazione di operazioni: panoramica
Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per le operazioni di inserimento, aggiornamento ed eliminazione basate su mapping. In pratica, tuttavia, la logica di business viene generalmente aggiunta per fornire sicurezza, convalida e così via.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]di seguito sono illustrate le tecniche di personalizzazione di queste operazioni.  
  
## <a name="loading-options"></a>Caricamento di opzioni  
 Nelle query è possibile controllare la quantità di dati relativi alla destinazione principale recuperata durante la connessione al database. Questa funzionalità viene ampiamente implementata usando <xref:System.Data.Linq.DataLoadOptions>. Per ulteriori informazioni, vedere [posticipata e il caricamento immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Metodi parziali  
 Nel mapping predefinito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono forniti metodi parziali per facilitare l'implementazione della logica di business. Per ulteriori informazioni, vedere [aggiunta Business logica da utilizzando i metodi parziali](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Stored procedure e funzioni definite dall'utente  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta l'utilizzo di stored procedure e funzioni definite dall'utente. Le stored procedure vengono solitamente usate per personalizzare operazioni. Per altre informazioni, vedere [Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Personalizzazione di inserimento, aggiornamento ed eliminazione di operazioni](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
