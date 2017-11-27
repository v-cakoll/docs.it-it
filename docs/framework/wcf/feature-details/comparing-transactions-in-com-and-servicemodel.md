---
title: Confronto di transazioni in COM+ e ServiceModel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a>Confronto di transazioni in COM+ e ServiceModel
In questo argomento viene illustrato come simulare il comportamento di un servizio COM+ transazionale usando gli attributi [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.  
  
## <a name="emulating-com-using-servicemodel-attributes"></a>Emulazione di COM+ mediante attributi ServiceModel  
 Nella tabella seguente viene confrontata l'enumerazione <xref:System.EnterpriseServices.TransactionOption> usata per creare una transazione `EnterpriseServices` e la modalità di correlazione agli attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forniti dallo spazio dei nomi <xref:System.ServiceModel>.  
  
|Attributo COM+|Attributi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]|  
|---------------------|------------------------------------------------------------------------|  
|RequiresNew|<xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `false`.|  
|Obbligatorio|<xref:System.ServiceModel.TransactionFlowAttribute> è impostato su <xref:System.ServiceModel.TransactionFlowOption.Allowed>.<br /><br /> <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `true`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `true`.|  
|Supportato|Non esiste alcun equivalente diretto. In generale, è necessario adottare il comportamento specificato per `Required`.|  
|NotSupported|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> è `false`.<br /><br /> L'attributo `TransactionFlow` nell'elemento di associazione è `false`.|  
|Disabled|Non esiste alcun equivalente diretto. In generale, è necessario adottare il comportamento specificato per `NotSupported`.|
