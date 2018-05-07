---
title: 'Procedura: Usare SystemParameters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 07b73d78a022e508f9ed8ca2e80b71bc2ab89910
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-systemparameters"></a>Procedura: Usare SystemParameters
In questo esempio viene illustrato come accedere e utilizzare le proprietà di <xref:System.Windows.SystemParameters> per applicare uno stile o personalizzare un pulsante.  
  
## <a name="example"></a>Esempio  
 Le risorse di sistema espongono diverse impostazioni basate sul sistema come risorse per consentire la creazione di oggetti visivi coerenti con le impostazioni del sistema. <xref:System.Windows.SystemParameters> è una classe che contiene le proprietà valore di parametro di sistema e le chiavi di risorsa che l'associazione ai valori. Ad esempio, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> è un <xref:System.Windows.SystemParameters> valore della proprietà e <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> è la chiave di risorsa corrispondente.  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile utilizzare i membri di <xref:System.Windows.SystemParameters> come l'utilizzo di una proprietà statica o un riferimento di risorsa dinamica (con il valore della proprietà statica come chiave). Usare un riferimento alla risorsa dinamica per aggiornare automaticamente il valore basato sul sistema durante l'esecuzione dell'applicazione; in caso contrario, usare un riferimento statico. Le chiavi di risorsa hanno il suffisso `Key` aggiunto al nome della proprietà.  
  
 Nell'esempio seguente viene illustrato come accedere e utilizzare i valori statici di <xref:System.Windows.SystemParameters> per applicare uno stile o personalizzare un pulsante. In questo esempio di markup con dimensioni applicando un pulsante <xref:System.Windows.SystemParameters> valori a un pulsante.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Utilizzare i valori di <xref:System.Windows.SystemParameters> nel codice, non è necessario utilizzare riferimenti statici o riferimenti a risorse dinamiche. Utilizzare invece i valori del <xref:System.Windows.SystemParameters> classe. Anche se le proprietà non chiave sono apparentemente definite come proprietà statiche, il comportamento di runtime [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come ospitata dal sistema verranno rivaluterà le proprietà in tempo reale e risponderà correttamente eseguita dall'utente. le modifiche ai valori di sistema. Nell'esempio seguente viene illustrato come impostare la larghezza e altezza di un pulsante utilizzando <xref:System.Windows.SystemParameters> valori.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.SystemParameters>  
 [Disegnare un'area con un pennello di sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Utilizzare la classe SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Usare chiavi dei parametri di sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
