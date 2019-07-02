---
title: 'Procedura: Creare una raccolta di tipi di carattere privata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 0bb7293a5423004a13cf98b79bba0a6c411a7c97
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505523"
---
# <a name="how-to-create-a-private-font-collection"></a>Procedura: Creare una raccolta di tipi di carattere privata
Il <xref:System.Drawing.Text.PrivateFontCollection> classe eredita dal <xref:System.Drawing.Text.FontCollection> classe base astratta. È possibile usare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto per mantenere un set di tipi di carattere specifico per l'applicazione. Una raccolta di caratteri privata può includere i tipi di carattere di sistema installati, nonché i tipi di carattere che non sono stati installati nel computer. Per aggiungere un file del tipo di carattere a una raccolta privata del tipo di carattere, chiamare il <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> metodo di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto contiene una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
 Il numero di famiglie di caratteri in una raccolta di tipo di carattere privato non è necessariamente lo stesso come il numero di file di caratteri che sono stati aggiunti alla raccolta. Ad esempio, si supponga di che aggiungono i file ArialBd.tff Times. tff e tff a una raccolta. Saranno presenti tre file, ma solo due famiglie nella raccolta perché Times. tff e tff appartengono alla stessa famiglia.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente aggiunge le seguenti tre file per un <xref:System.Drawing.Text.PrivateFontCollection> oggetto:  
  
- C:\\*systemroot*\Fonts\Arial.tff (Arial, normale)  
  
- C:\\*systemroot*\Fonts\CourBI.tff (Courier New, grassetto corsivo)  
  
- C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)  
  
 Il codice recupera una matrice di <xref:System.Drawing.FontFamily> oggetti dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà del <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 Per ognuno <xref:System.Drawing.FontFamily> oggetto nella raccolta, il codice chiama il <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo per determinare se sono disponibili vari stili (normale, grassetto, corsivo, grassetto corsivo, sottolineato e barrato). Gli argomenti passati per il <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo sono membri del <xref:System.Drawing.FontStyle> enumerazione.  
  
 Se una combinazione di famiglia/stile specificato è disponibile, un <xref:System.Drawing.Font> costruito utilizzando tale famiglia e lo stile. Il primo argomento passato per il <xref:System.Drawing.Font.%23ctor%2A> costruttore è il nome della famiglia (non un <xref:System.Drawing.FontFamily> dell'oggetto come avviene per altre varianti del <xref:System.Drawing.Font.%23ctor%2A> costruttore). Dopo il <xref:System.Drawing.Font> costruito, viene passata al <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> classe per visualizzare il nome della famiglia insieme al nome dello stile.  
  
 L'output del codice seguente è simile all'output illustrato nella figura seguente:  
  
 ![Screenshot che mostra il testo in vari tipi di carattere.](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 Tff (è stato aggiunto alla raccolta del tipo di carattere privato nell'esempio di codice seguente) è il file del tipo di carattere per lo stile regolare Arial. Si noti tuttavia che l'output del programma illustra alcuni stili disponibili diverso dal normale per il tipo di carattere Arial. Ciò avviene perché GDI+ possono simulare gli stili grassetto, corsivo e grassetto corsivo dallo stile regolare. GDI+ può inoltre generare barrati e dallo stile regolare.  
  
 Analogamente, GDI+ possono simulare lo stile grassetto corsivo dallo stile grassetto o corsivo. Viene illustrato l'output del programma che lo stile grassetto corsivo è disponibile per la famiglia di volte in cui anche se tff (Times New Roman, in grassetto) è l'unico file volte nella raccolta.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Text.PrivateFontCollection>
- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
