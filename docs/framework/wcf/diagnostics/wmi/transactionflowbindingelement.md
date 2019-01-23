---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514570"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
 Tipo di accesso: Sola lettura  
  
 Specifica il requisito per un'intestazione dei token di sicurezza emessi (IssuedTokens da WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Protocollo delle transazioni utilizzato dal servizio per il flusso delle transazioni.  
  
### <a name="transactions"></a>Transazioni  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Indica se la transazione in ingresso è supportata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
