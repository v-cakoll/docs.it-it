---
title: 'Procedura: Implementare la logica di convalida negli oggetti personalizzati'
ms.date: 08/02/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: e2b77ef65c92ae596c5620c9122dcf3db0bf9462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525989"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Procedura: Implementare la logica di convalida negli oggetti personalizzati
In questo esempio viene illustrato come implementare la logica di convalida in un oggetto personalizzato e quindi eseguire l'associazione.  
  
## <a name="example"></a>Esempio  
 È possibile fornire la logica di convalida a livello aziendale, se l'oggetto di origine implementa <xref:System.ComponentModel.IDataErrorInfo>, come illustrato nell'esempio seguente, che definisce un `Person` oggetto che implementa <xref:System.ComponentModel.IDataErrorInfo>:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Nell'esempio seguente associa la proprietà text della casella di testo per il `Person.Age` proprietà, che è stato reso disponibile per l'associazione tramite una dichiarazione della risorsa cui viene assegnata il `x:Key` `data`. Il <xref:System.Windows.Controls.DataErrorValidationRule> verifica la presenza di errori di convalida generati dal <xref:System.ComponentModel.IDataErrorInfo> implementazione.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 In alternativa, invece di usare la <xref:System.Windows.Controls.DataErrorValidationRule>, è possibile impostare il <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà `true`.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [Implementare la convalida dell'associazione](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
