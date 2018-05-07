---
title: "Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: a42fee8ad31dcc02459711fc51e8611e0e8cd012
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione
Questo esempio illustra come definire e usare un dizionario risorse personalizzato dell'ambito di un'applicazione.  
  
## <a name="example"></a>Esempio  
 <xref:System.Windows.Application> espone un archivio di applicazione per le risorse condivise: <xref:System.Windows.Application.Resources%2A>. Per impostazione predefinita, il <xref:System.Windows.Application.Resources%2A> proprietà viene inizializzata con un'istanza di <xref:System.Windows.ResourceDictionary> tipo. Utilizzare questa istanza quando si ottengono e impostare le proprietà dell'ambito dell'applicazione utilizzando <xref:System.Windows.Application.Resources%2A>. Per ulteriori informazioni, vedere [procedura: ottenere e impostare una risorsa applicazione](http://msdn.microsoft.com/library/39e0420c-c9fc-47dc-8956-fdd95b214095).
  
 Se si dispongono di più risorse impostate tramite la <xref:System.Windows.Application.Resources%2A>, è invece possibile utilizzare un dizionario risorse personalizzato per archiviare le risorse e impostare <xref:System.Windows.Application.Resources%2A> con esso invece. Di seguito viene illustrato come dichiarare un dizionario risorse personalizzato tramite XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Lo scambio di interi dizionari risorse tramite <xref:System.Windows.Application.Resources%2A> consente di supportare l'applicazione di temi, dove ogni tema è incapsulato da un singolo dizionario risorse. Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Nell'esempio seguente viene illustrato come ottenere le risorse dell'ambito di applicazione dal dizionario risorse esposto da <xref:System.Windows.Application.Resources%2A> in XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 L'esempio seguente illustra come è possibile ottenere anche le risorse nel codice.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Esistono due considerazioni quando si utilizza <xref:System.Windows.Application.Resources%2A>. Innanzitutto, il dizionario *chiave* è un oggetto, pertanto è necessario usare esattamente la stessa istanza dell'oggetto sia quando l'impostazione e recupero di un valore della proprietà. (si noti che la chiave fa distinzione tra maiuscole e minuscole quando si usa una stringa). In secondo luogo, il dizionario *valore* è un oggetto, pertanto è necessario convertire il valore per il tipo desiderato quando si recupera un valore della proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Dizionari risorse uniti](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
