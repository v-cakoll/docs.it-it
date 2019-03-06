---
title: "Procedura: Utilizzare un dizionario di risorse dell'ambito dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: a2453ae7fad56205ae06835d8710ca126bba17c7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369734"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Procedura: Utilizzare un dizionario di risorse dell'ambito dell'applicazione
Questo esempio illustra come definire e usare un dizionario risorse personalizzato dell'ambito di un'applicazione.  
  
## <a name="example"></a>Esempio  
 <xref:System.Windows.Application> espone un archivio di ambito dell'applicazione per le risorse condivise: <xref:System.Windows.Application.Resources%2A>. Per impostazione predefinita, il <xref:System.Windows.Application.Resources%2A> proprietà viene inizializzata con un'istanza di <xref:System.Windows.ResourceDictionary> tipo. Utilizzare questa istanza quando si ottengono e impostano le proprietà dell'ambito dell'applicazione utilizzando <xref:System.Windows.Application.Resources%2A>. Per altre informazioni, vedere [Procedura: Ottenere e impostare una risorsa applicazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Se si dispongono di più risorse impostate mediante <xref:System.Windows.Application.Resources%2A>, è invece possibile utilizzare un dizionario risorse personalizzato per archiviare tali risorse e impostare <xref:System.Windows.Application.Resources%2A> con esso invece. Di seguito viene illustrato come dichiarare un dizionario risorse personalizzato usando XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Lo scambio di interi dizionari risorse mediante <xref:System.Windows.Application.Resources%2A> consente di supportare temi dell'ambito dell'applicazione, dove ogni tema è incapsulato da un unico dizionario risorse. Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Di seguito viene illustrato come ottenere le risorse dell'ambito dell'applicazione dal dizionario risorse esposto da <xref:System.Windows.Application.Resources%2A> in XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 L'esempio seguente illustra come è possibile ottenere anche le risorse nel codice.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Esistono due aspetti da considerare quando si usa <xref:System.Windows.Application.Resources%2A>. Per prima cosa, il dizionario *chiave* è un oggetto, pertanto è necessario usare esattamente la stessa istanza dell'oggetto sia quando si imposta e ottiene un valore della proprietà. (si noti che la chiave fa distinzione tra maiuscole e minuscole quando si usa una stringa). In secondo luogo, il dizionario *valore* è un oggetto, pertanto è necessario convertire il valore al tipo desiderato quando si recupera un valore della proprietà.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Risorse XAML](../advanced/xaml-resources.md)
- [Dizionari risorse uniti](../advanced/merged-resource-dictionaries.md)
