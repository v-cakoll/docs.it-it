---
title: Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 4fe79c74b6ff634223a4f10d8c5dc54bb77571cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822287"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione
Un oggetto viene assegnato a una variabile dichiarata di tipo i [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Quando si dichiara una variabile come `Object`, il compilatore deve eseguire *associazione tardiva*, in modo che operazioni supplementari in fase di esecuzione. Espone inoltre l'applicazione a possibili errori di runtime. Ad esempio, se si assegna un <xref:System.Windows.Forms.Form> per il `Object` variabile e quindi tenta di accedere il <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> proprietà, il runtime genera una <xref:System.MemberAccessException> perché la <xref:System.Windows.Forms.Form> classe non espone un `NameTable` proprietà.  
  
 Se si dichiara la variabile di un tipo specifico, il compilatore può eseguire *associazione anticipata* in fase di compilazione. Ciò comporta un miglioramento delle prestazioni, controllo dell'accesso ai membri del tipo specifico e una migliore leggibilità del codice.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42017  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Se possibile, dichiarare la variabile di un tipo specifico.  
  
## <a name="see-also"></a>Vedere anche

- [Associazione anticipata e tardiva](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Dichiarazione di variabili oggetto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
