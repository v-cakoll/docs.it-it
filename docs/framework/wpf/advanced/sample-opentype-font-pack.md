---
title: Esempio di pacchetto di tipi di carattere OpenType
ms.date: 03/30/2017
helpviewer_keywords:
- OpenType font pack [WPF]
- fonts [WPF], OpenType font pack
- typography [WPF], OpenType font pack
ms.assetid: 56b46fa1-a44e-419b-8f14-25ad51c715c3
ms.openlocfilehash: e2b3dc3b95cf81a60494f7a02488067717938e97
ms.sourcegitcommit: 43761fcee10aeefcf851ea81cea3f3c691420856
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "69545230"
---
# <a name="sample-opentype-font-pack"></a>Esempio di pacchetto di tipi di carattere OpenType
In questo argomento viene fornita una panoramica dei tipi di carattere OpenType di esempio distribuiti [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)]con. I tipi di carattere di esempio supportano le funzionalità OpenType estese [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] che possono essere utilizzate dalle applicazioni.  

<a name="overview"></a>   
## <a name="fonts-in-the-opentype-font-pack"></a>Tipi di carattere nel pacchetto di caratteri OpenType  
 In [!INCLUDE[TLA2#tla_wcsdk](../../../../includes/tla2sharptla-wcsdk-md.md)] è disponibile un set di tipi di carattere OpenType di esempio che è [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] possibile utilizzare per la creazione di applicazioni. I tipi di carattere di esempio sono concessi in licenza da Ascender Corporation. Questi tipi di carattere implementano solo un subset delle funzionalità totali definite dal formato OpenType. Nella tabella seguente sono elencati i nomi dei tipi di carattere OpenType di esempio.  
  
|**Nome**|**File**|  
|--------------|--------------|  
|Kootenay|Kooten.ttf|  
|Lindsey|Linds.ttf|  
|Miramonte|Miramo.ttf|  
|Miramonte Bold|Miramob.ttf|  
|Pericles|Peric.ttf|  
|Pericles Light|Pericl.ttf|  
|Pescadero|Pesca.ttf|  
|Pescadero Bold|Pescab.ttf|  
  
 La figura seguente mostra l'aspetto dei tipi di carattere OpenType di esempio.  
  
 ![Elenco di nomi di carattere nel pacchetto di caratteri di esempio](./media/sample-opentype-font-pack/font-names-sample-pack.gif)  
  
 I tipi di carattere di esempio sono concessi in licenza da Ascender Corporation. Ascender è un provider di tipi di carattere avanzati. Per ottenere in licenza versioni estese o personalizzate dei tipi di carattere di esempio, vedere il [sito Web di Ascender Corporation](https://go.microsoft.com/fwlink/?LinkId=182627).  
  
> [!NOTE]
>  È responsabilità degli sviluppatori verificare di disporre dei diritti di licenza necessari per qualsiasi tipo di carattere incorporato all'interno di un'applicazione o ridistribuito in altro modo.  
  
<a name="installing_the_fonts"></a>   
## <a name="installing-the-fonts"></a>Installazione dei tipi di carattere  
 È possibile installare i tipi di carattere OpenType di esempio nella directory dei [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] tipi di carattere predefinita, **\Windows\Fonts**. Per l'installazione, usare il pannello di controllo Tipi di carattere. Dopo l'installazione nel computer, questi tipi di carattere saranno accessibili a tutte le applicazioni che fanno riferimento ai tipi di carattere predefiniti di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. È possibile visualizzare un set di caratteri rappresentativo in diverse dimensioni facendo doppio clic sul file del tipo di carattere. La screenshot seguente mostra il file del tipo di carattere Lindsey, ovvero Linds.ttf.  
  
 ![ &#40;OpenType&#41; tipo di carattere Lindsey](./media/typographyinwpf-04.png "TypographyInWPF_04")  
Visualizzazione del tipo di carattere Lindsey  
  
<a name="using_the_fonts"></a>   
## <a name="using-the-fonts"></a>Uso dei tipi di carattere  
 Nell'applicazione si possono usare i tipi di carattere in due modi. È possibile aggiungere tipi di carattere all'applicazione come elementi di contenuto del progetto non incorporati come risorse in un assembly. In alternativa, si possono aggiungere tipi di carattere all'applicazione come elementi risorsa del progetto incorporati nei file di assembly dell'applicazione. Per altre informazioni, vedere [Includere i tipi di carattere nel pacchetto delle applicazioni](packaging-fonts-with-applications.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Documents.Typography>
- [Funzionalità dei tipi di carattere OpenType](opentype-font-features.md)
- [Includere i tipi di carattere nel pacchetto delle applicazioni](packaging-fonts-with-applications.md)
