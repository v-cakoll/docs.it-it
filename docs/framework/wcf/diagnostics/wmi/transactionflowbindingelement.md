---
title: TransactionFlowBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b073efc47ccc1708bf4c58153b1001a21eee25f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe TransactionFlowBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe TransactionFlowBindingElement dispone delle proprietà seguenti:  
  
### <a name="issuedtokens"></a>IssuedTokens  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.  
  
### <a name="transactions"></a>Transazioni  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se la transazione in ingresso è supportata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
