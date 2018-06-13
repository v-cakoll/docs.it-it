---
title: 'Procedura: implementare la logica di convalida negli oggetti personalizzati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555964"
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
