---
title: 'Procedura: creare una raccolta di caratteri privata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 824d42c40b07e8662395e7a1286b9a5a6112c415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-private-font-collection"></a>Procedura: creare una raccolta di caratteri privata
Il <xref:System.Drawing.Text.PrivateFontCollection> classe eredita la <xref:System.Drawing.Text.FontCollection> classe base astratta. È possibile utilizzare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto per mantenere un set di caratteri specifico per l'applicazione. Un insieme di caratteri privata può includere i caratteri di sistema installati, nonché i tipi di carattere che non sono stati installati nel computer. Per aggiungere un file di caratteri a un insieme di caratteri privata, chiamare il <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> metodo di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto contiene una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
 Il numero di famiglie di caratteri in una raccolta di tipo di carattere privato non è necessariamente lo stesso numero di file di caratteri che sono stati aggiunti alla raccolta. Ad esempio, si supponga di che aggiungono i file ArialBd. tff, Times. tff e TimesBd a una raccolta. Saranno presenti tre file ma solo due gruppi nella raccolta poiché Times. tff e TimesBd appartengono alla stessa famiglia.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge i file seguenti tre tipi di carattere per un <xref:System.Drawing.Text.PrivateFontCollection> oggetto:  
  
-   C:\\*systemroot*\Fonts\Arial.tff (Arial, normale)  
  
-   C:\\*systemroot*\Fonts\CourBI.tff (Courier New, grassetto corsivo)  
  
-   C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, grassetto)  
  
 Il codice recupera una matrice di <xref:System.Drawing.FontFamily> oggetti dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà del <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 Per ogni <xref:System.Drawing.FontFamily> oggetto nella raccolta, il codice chiama il <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo per determinare se sono disponibili vari stili (normale, grassetto, corsivo, corsivo grassetto, sottolineato e barrato). Gli argomenti passati al <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo sono membri del <xref:System.Drawing.FontStyle> enumerazione.  
  
 Se una combinazione di gruppo e stile specificato è disponibile, un <xref:System.Drawing.Font> oggetto viene costruito utilizzando quel gruppo e lo stile. Il primo argomento passato per il <xref:System.Drawing.Font.%23ctor%2A> costruttore è il nome della famiglia (non un <xref:System.Drawing.FontFamily> oggetto come accade per altre varianti del <xref:System.Drawing.Font.%23ctor%2A> costruttore). Dopo il <xref:System.Drawing.Font> viene creato l'oggetto, viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo la <xref:System.Drawing.Graphics> classe per visualizzare il nome di famiglia insieme al nome dello stile.  
  
 L'output del codice seguente è simile a quello illustrato nella figura seguente.  
  
 ![Testo caratteri](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")  
  
 Tff (aggiunto alla raccolta di tipo di carattere privato nell'esempio di codice seguente) è il file di tipo di carattere per lo stile normale Arial. Si noti tuttavia che l'output del programma mostra alcuni stili disponibili diverso da normale, per la famiglia. Ciò accade perché [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] possibile simulare il grassetto, corsivo e grassetto, corsivo dallo stile normale. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] può inoltre generare barrati e dallo stile normale.  
  
 Analogamente, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] possibile simulare lo stile grassetto corsivo lo stile grassetto o corsivo. L'output del programma indica che lo stile grassetto corsivo è disponibile per la famiglia di volte in cui anche se tff (Times New Roman, grassetto) è l'unico file volte nella raccolta.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
