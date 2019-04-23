---
title: Istanze
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975585"
---
# <a name="instances"></a>Istanze
Nome contatore: istanze.  
  
## <a name="description"></a>Descrizione  
 Numero di contesti di istanza attualmente contenuti dal servizio.  
  
 In genere, il numero di contesti di istanza è identico al numero di istanze. Tuttavia, gli scenari seguenti rappresenta un'eccezione a questa regola.  
  
-   Un metodo di servizio chiama il metodo <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> in modo esplicito.  
  
-   Viene applicata un'enumerazione <xref:System.ServiceModel.ReleaseInstanceMode> a un'istanza di <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.OperationBehaviorAttribute>
