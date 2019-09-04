---
title: 'Personalizzazione di operazioni: Panoramica'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 48116887471709c60c9666f68c7ebdd0e6d128a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70247521"
---
# <a name="customizing-operations-overview"></a>Personalizzazione di operazioni: Panoramica
Per impostazione predefinita, in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene generato codice SQL dinamico per le operazioni di inserimento, aggiornamento ed eliminazione basate su mapping. In pratica, tuttavia, la logica di business viene generalmente aggiunta per fornire sicurezza, convalida e così via.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]di seguito sono riportate le tecniche per la personalizzazione di queste operazioni.  
  
## <a name="loading-options"></a>Caricamento di opzioni  
 Nelle query è possibile controllare la quantità di dati relativi alla destinazione principale recuperata durante la connessione al database. Questa funzionalità viene ampiamente implementata usando <xref:System.Data.Linq.DataLoadOptions>. Per ulteriori informazioni, vedere il [caricamento posticipato rispetto al caricamento immediato](deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Metodi parziali  
 Nel mapping predefinito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono forniti metodi parziali per facilitare l'implementazione della logica di business. Per ulteriori informazioni, vedere [aggiunta di logica di business utilizzando metodi parziali](adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Stored procedure e funzioni definite dall'utente  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]supporta l'utilizzo di stored procedure e funzioni definite dall'utente. Le stored procedure vengono solitamente usate per personalizzare operazioni. Per altre informazioni, vedere [Stored procedure](stored-procedures.md).  
  
## <a name="see-also"></a>Vedere anche

- [Personalizzazione di operazioni di inserimento, aggiornamento ed eliminazione](customizing-insert-update-and-delete-operations.md)
