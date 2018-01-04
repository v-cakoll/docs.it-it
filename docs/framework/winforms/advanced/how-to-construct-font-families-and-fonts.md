---
title: 'Procedura: creare caratteri e gruppi di caratteri'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e152c525550554082d7d6c38a972ccc150adabb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-construct-font-families-and-fonts"></a>Procedura: creare caratteri e gruppi di caratteri
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]i caratteri con lo stesso carattere tipografico ma stili diversi in famiglie di caratteri. Ad esempio, la famiglia contiene i caratteri seguenti:  
  
-   Arial normale  
  
-   Arial grassetto  
  
-   Arial corsivo  
  
-   Arial grassetto corsivo  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]vengono utilizzati quattro stili per creare i gruppi: normale, grassetto, corsivo e grassetto corsivo. Aggettivi come *restringere* e *arrotondato* non sono considerati stili; piuttosto fanno parte del nome di famiglia. Ad esempio, Arial Narrow è una famiglia di caratteri con i membri seguenti:  
  
-   Arial normale "narrow"  
  
-   "Narrow" Arial grassetto  
  
-   Arial corsivo "narrow"  
  
-   Arial Narrow grassetto corsivo  
  
 Prima di poter creare testo con [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è necessario costruire un <xref:System.Drawing.FontFamily> oggetto e un <xref:System.Drawing.Font> oggetto. Il <xref:System.Drawing.FontFamily> oggetto specifica il tipo di carattere (ad esempio, Arial) e <xref:System.Drawing.Font> oggetto specifica la dimensione, stile e unità.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un stile normale carattere con dimensioni pari a 16 pixel. Nel codice seguente, il primo argomento passato per il <xref:System.Drawing.Font.%23ctor%2A> costruttore è la <xref:System.Drawing.FontFamily> oggetto. Il secondo argomento specifica le dimensioni del carattere, misurata in unità identificata dal quarto argomento. Il terzo argomento identificato lo stile.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel>è un membro del <xref:System.Drawing.GraphicsUnit> enumerazione, e <xref:System.Drawing.FontStyle.Regular> è membro il <xref:System.Drawing.FontStyle> enumerazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Grafica e disegno in Windows Form](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
