---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: c2fb32c4c693cbfc487ce89b36f013398cbdb703
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485619"
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
