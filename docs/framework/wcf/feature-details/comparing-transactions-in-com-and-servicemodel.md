---
title: Confronto di transazioni in COM+ e ServiceModel
ms.date: 03/30/2017
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
ms.openlocfilehash: 4a47fe1686dff2e705b06b001d7d5e4ea6e8c5f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488647"
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Confronto di transazioni in COM+ e ServiceModel
In questo argomento viene illustrato come simulare il comportamento di un servizio COM+ transazionale usando gli attributi di Windows Communication Foundation (WCF) di <xref:System.ServiceModel> fornisce lo spazio dei nomi.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulazione di COM+ mediante attributi ServiceModel  
 Nella tabella seguente vengono confrontati i <xref:System.EnterpriseServices.TransactionOption> enumerazione utilizzata per creare un' `EnterpriseServices` delle transazioni e modalità di correlazione agli attributi WCF il <xref:System.ServiceModel> fornisce lo spazio dei nomi.  
  
|Attributo COM+|Attributi WCF|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `false`.|  
|Obbligatorio|<xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `true`.|  
|Supportato|Non esiste alcun equivalente diretto. In generale, è necessario adottare il comportamento specificato per `Required`.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `false`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `false`.|  
|Disabled|Non esiste alcun equivalente diretto. In generale, è necessario adottare il comportamento specificato per `NotSupported`.|
