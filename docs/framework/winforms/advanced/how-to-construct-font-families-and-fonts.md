---
title: 'Procedura: Creare tipi di carattere e famiglie di caratteri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 0a9dcd00d4bc3e64ae4fc9a1d4884fac18521825
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181220"
---
# <a name="how-to-construct-font-families-and-fonts"></a>Procedura: Creare tipi di carattere e famiglie di caratteri
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Raggruppa i tipi di carattere con lo stesso carattere tipografico, ma diversi stili in famiglie di caratteri. Ad esempio, il tipo di carattere Arial contiene i tipi di carattere seguenti:  
  
-   Arial normale  
  
-   Arial in grassetto  
  
-   Arial corsivo  
  
-   Arial grassetto corsivo  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] vengono utilizzati quattro stili per creare i gruppi: normale, grassetto, corsivo e grassetto corsivo. Aggettivi, ad esempio *restringere* e *arrotondato* non vengono considerati gli stili, piuttosto fanno parte del nome della famiglia. Ad esempio, Arial ristretto è una famiglia di caratteri con i membri seguenti:  
  
-   Arial normale ridotta  
  
-   Arial "narrow" grassetto  
  
-   Corsivo Narrow Arial  
  
-   Arial Narrow grassetto corsivo  
  
 Prima di poter creare testo con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario costruire una <xref:System.Drawing.FontFamily> oggetto e un <xref:System.Drawing.Font> oggetto. Il <xref:System.Drawing.FontFamily> oggetto specifica il carattere tipografico (ad esempio, Arial) e il <xref:System.Drawing.Font> oggetto specifica le dimensioni, stile e unità.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente crea uno stile regolare del tipo di carattere Arial con dimensioni pari a 16 pixel. Nel codice seguente, il primo argomento passato per il <xref:System.Drawing.Font.%23ctor%2A> costruttore è la <xref:System.Drawing.FontFamily> oggetto. Il secondo argomento specifica le dimensioni del font misurata nelle unità specificate dal quarto argomento. Il terzo argomento identificato lo stile.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> è un membro del <xref:System.Drawing.GraphicsUnit> enumerazione, e <xref:System.Drawing.FontStyle.Regular> è un membro del <xref:System.Drawing.FontStyle> enumerazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
