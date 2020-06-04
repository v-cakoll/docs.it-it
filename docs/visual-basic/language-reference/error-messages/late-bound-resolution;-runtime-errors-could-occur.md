---
title: Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: f1dc656a09eee05080356892b280a79505f3b9cd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397350"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Risoluzione ad associazione tardiva; potrebbero verificarsi degli errori in fase di esecuzione
Un oggetto viene assegnato a una variabile dichiarata come [tipo di dati Object](../data-types/object-data-type.md).  
  
 Quando si dichiara una variabile come `Object` , il compilatore deve eseguire un' *associazione tardiva*, causando operazioni aggiuntive in fase di esecuzione. Espone inoltre l'applicazione a possibili errori di runtime. Se ad esempio si assegna un oggetto <xref:System.Windows.Forms.Form> alla `Object` variabile e quindi si tenta di accedere alla <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> proprietà, il runtime genera un'eccezione <xref:System.MemberAccessException> perché la <xref:System.Windows.Forms.Form> classe non espone una `NameTable` Proprietà.  
  
 Se si dichiara che la variabile è di un tipo specifico, il compilatore può eseguire un' *associazione anticipata* in fase di compilazione. Ciò comporta un miglioramento delle prestazioni, l'accesso controllato ai membri del tipo specifico e una migliore leggibilità del codice.  
  
 Per impostazione predefinita, si tratta di un messaggio di avviso. Per informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC42017  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Se possibile, dichiarare la variabile in modo che sia di un tipo specifico.  
  
## <a name="see-also"></a>Vedere anche

- [Associazione anticipata e tardiva](../../programming-guide/language-features/early-late-binding/index.md)
- [Dichiarazione di variabili oggetto](../../programming-guide/language-features/variables/object-variable-declaration.md)
