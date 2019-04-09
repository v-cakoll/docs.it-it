---
title: Tipo XAML intrinseco x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 7bb78b05be7b3edc4471bc276010eabd92a07a14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145236"
---
# <a name="xcode-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:Code
Consente il posizionamento del codice all'interno di una produzione XAML. Tale codice può essere compilato da qualsiasi implementazione di processore XAML che consente la compilazione XAML o a sinistra in produzione XAML per utilizzi successivi, ad esempio interpretazione da un runtime.  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Note  
 Il codice all'interno di `x:Code` elemento della direttiva XAML viene sempre interpretato nello spazio dei nomi XML generale e gli spazi dei nomi XAML specificato. Pertanto, in genere è necessario racchiudere il codice usato per `x:Code` all'interno di un `CDATA` segmento.  
  
 `x:Code` non è consentito per tutti i possibili meccanismi di distribuzione di una produzione XAML. Il codice deve essere compilato nel framework specifici (ad esempio WPF). In altri Framework, `x:Code` utilizzo potrebbe essere impedito a livello generale.  
  
 Per i framework che consentono a managed `x:Code` il contenuto, il compilatore di linguaggio corretto da usare per `x:Code` contenuto è determinato dalle impostazioni e le destinazioni del progetto che lo contiene viene usato per compilare l'applicazione.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Codice dichiarati all'interno di `x:Code` per WPF ha alcune limitazioni rilevanti:  
  
-   Il `x:Code` elemento della direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.  
  
-   [Direttiva X:Class](x-class-directive.md) deve essere fornita per l'elemento radice padre.  
  
-   Il codice inserito all'interno di `x:Code` verrà considerato dalla compilazione per rientrare nell'ambito della classe parziale che è già creata per la pagina XAML. Di conseguenza deve essere tutto il codice che è definire membri o le variabili di tale classe parziale.  
  
-   Non è possibile definire altre classi, diverso da una classe all'interno della classe parziale di annidamento (è consentito l'annidamento, ma non accade in genere perché le classi annidate non possono essere fatto riferimento in XAML). Spazi dei nomi CLR nomi diverso da quello utilizzato per la classe parziale esistente non può essere definita o aggiungere.  
  
-   I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR classe parziale devono essere completi. Se i membri dichiarati sono gli override per i membri di classe parziale sottoponibile a override, questo deve essere specificato con la parola chiave override specifico del linguaggio. Se i membri dichiarati `x:Code` ambito sono in conflitto con i membri della classe parziale creato di fuori di XAML, in modo che il compilatore segnala il conflitto, il file XAML non è possibile compilare o caricare.  
  
## <a name="see-also"></a>Vedere anche

- [Direttiva x:Class](x-class-directive.md)
- [Code-behind e XAML in WPF](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [Panoramica di XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
