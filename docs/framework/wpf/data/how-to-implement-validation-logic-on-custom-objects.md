---
title: 'Procedura: implementare la logica di convalida negli oggetti personalizzati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5044339e1d06bddad05151b2db99d5f96d068e77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Procedura: implementare la logica di convalida negli oggetti personalizzati
In questo esempio viene illustrato come implementare la logica di convalida in un oggetto personalizzato e quindi eseguire l'associazione.  
  
## <a name="example"></a>Esempio  
 È possibile fornire la logica di convalida a livello aziendale se l'oggetto di origine implementa <xref:System.ComponentModel.IDataErrorInfo>, come nell'esempio seguente:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Nell'esempio seguente, la proprietà text della casella di testo viene associata al `Age` proprietà del `Person` oggetto, che è stato reso disponibile per l'associazione tramite una dichiarazione di risorsa che viene assegnata il `x:Key``data`. Il <xref:System.Windows.Controls.DataErrorValidationRule> verifica la presenza di errori di convalida generati dal <xref:System.ComponentModel.IDataErrorInfo> implementazione.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 In alternativa, anziché il <xref:System.Windows.Controls.DataErrorValidationRule>, è possibile impostare il <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà `true`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [Implementare la convalida dell'associazione](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
