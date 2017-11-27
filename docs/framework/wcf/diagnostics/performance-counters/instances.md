---
title: Istanze
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 23182f18f28cfb843c1c3a70996590a92d9cdea8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="instances"></a>Istanze
Nome contatore: istanze.  
  
## <a name="description"></a>Descrizione  
 Numero di contesti di istanza attualmente contenuti dal servizio.  
  
 In genere, il numero di contesti di istanza è identico al numero di istanze. Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.  
  
-   Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.  
  
-   Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
