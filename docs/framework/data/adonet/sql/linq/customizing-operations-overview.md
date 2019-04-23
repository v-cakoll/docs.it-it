---
title: 'Personalizzazione di operazioni: Panoramica'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 29fb75271b7bc324d462078e94e4a28534986fba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075977"
---
# <a name="customizing-operations-overview"></a>Personalizzazione di operazioni: Panoramica
Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per le operazioni di inserimento, aggiornamento ed eliminazione basate su mapping. In pratica, tuttavia, la logica di business viene generalmente aggiunta per fornire sicurezza, convalida e così via.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] di seguito sono elencate le tecniche per la personalizzazione di queste operazioni.  
  
## <a name="loading-options"></a>Caricamento di opzioni  
 Nelle query è possibile controllare la quantità di dati relativi alla destinazione principale recuperata durante la connessione al database. Questa funzionalità viene ampiamente implementata usando <xref:System.Data.Linq.DataLoadOptions>. Per altre informazioni, vedere [posticipato e immediato caricamento](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Metodi parziali  
 Nel mapping predefinito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono forniti metodi parziali per facilitare l'implementazione della logica di business. Per altre informazioni, vedere [aggiunta di Business per la logica da usando i metodi parziali](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Stored procedure e funzioni definite dall'utente  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta l'utilizzo di stored procedure e funzioni definite dall'utente. Le stored procedure vengono solitamente usate per personalizzare operazioni. Per altre informazioni, vedere [Stored procedure](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Vedere anche

- [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
