---
title: "Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione"
description: Informazioni su come definire e usare un dizionario risorse personalizzato con ambito applicazione in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 9d117dea6c554339b4b462b9bf37b80da2dc477f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85613709"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Procedura: utilizzare un dizionario risorse relativo all'ambito dell'applicazione
Questo esempio illustra come definire e usare un dizionario risorse personalizzato dell'ambito di un'applicazione.  
  
## <a name="example"></a>Esempio  
 <xref:System.Windows.Application>espone un archivio dell'ambito dell'applicazione per le risorse condivise: <xref:System.Windows.Application.Resources%2A> . Per impostazione predefinita, la <xref:System.Windows.Application.Resources%2A> proprietà viene inizializzata con un'istanza del <xref:System.Windows.ResourceDictionary> tipo. Usare questa istanza quando si ottengono e si impostano le proprietà dell'ambito dell'applicazione usando <xref:System.Windows.Application.Resources%2A> . Per altre informazioni, vedere [procedura: ottenere e impostare una risorsa dell'ambito dell'applicazione](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 Se si dispone di più risorse impostate utilizzando <xref:System.Windows.Application.Resources%2A> , è invece possibile utilizzare un dizionario risorse personalizzato per archiviare tali risorse e impostarle <xref:System.Windows.Application.Resources%2A> in alternativa. Di seguito viene illustrato come dichiarare un dizionario risorse personalizzato con XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Lo scambio di interi dizionari risorse tramite <xref:System.Windows.Application.Resources%2A> consente di supportare i temi dell'ambito dell'applicazione, in cui ogni tema è incapsulato da un singolo dizionario risorse. Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Di seguito viene illustrato come ottenere le risorse dell'ambito dell'applicazione dal dizionario risorse esposto da <xref:System.Windows.Application.Resources%2A> in XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 L'esempio seguente illustra come è possibile ottenere anche le risorse nel codice.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Quando si usa, è necessario tenere presenti due considerazioni <xref:System.Windows.Application.Resources%2A> . In primo luogo, la *chiave* del dizionario è un oggetto, pertanto è necessario usare esattamente la stessa istanza dell'oggetto quando si imposta e si recupera un valore della proprietà. Si noti che la chiave fa distinzione tra maiuscole e minuscole quando si usa una stringa. In secondo luogo, il *valore* del dizionario è un oggetto, pertanto è necessario convertire il valore nel tipo desiderato quando si recupera un valore della proprietà.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Dizionari risorse uniti](../advanced/merged-resource-dictionaries.md)
