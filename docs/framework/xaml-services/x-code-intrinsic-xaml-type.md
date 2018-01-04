---
title: Tipo XAML intrinseco x:Code
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
caps.latest.revision: "19"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d39249a5d1c0e230d21e6d889b92d0b57c98e2ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="xcode-intrinsic-xaml-type"></a>Tipo XAML intrinseco x:Code
Consente il posizionamento del codice all'interno di una produzione XAML. Tale codice può essere compilato da qualsiasi implementazione del processore XAML che compila XAML o a sinistra nella produzione XAML per utilizzi successivi, ad esempio l'interpretazione di un runtime.  
  
## <a name="xaml-object-element-usage"></a>Utilizzo della sintassi XAML per gli elementi oggetto  
  
```  
<x:Code>  
   // code instructions, usually enclosed by CDATA...  
</x:Code>  
```  
  
## <a name="remarks"></a>Note  
 Il codice all'interno di `x:Code` elemento della direttiva XAML viene comunque interpretato nello spazio dei nomi XML generale e gli spazi dei nomi XAML fornito. Pertanto, in genere è necessario racchiudere il codice utilizzato per `x:Code` all'interno di un `CDATA` segmento.  
  
 `x:Code`non è consentito per tutti i meccanismi di distribuzione di una produzione XAML. Il codice deve essere compilato nel framework specifici (ad esempio WPF). In altri Framework, `x:Code` utilizzo potrebbe essere in genere non consentito.  
  
 Per i framework che consentono a gestito `x:Code` il contenuto, il compilatore di linguaggio corretto da utilizzare per `x:Code` contenuto è determinato dalle impostazioni e le destinazioni del progetto utilizzato per compilare l'applicazione contenitore.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 Codice dichiarato all'interno di `x:Code` per WPF presenta molte limitazioni rilevanti:  
  
-   Il `x:Code` elemento della direttiva deve essere un elemento figlio immediato dell'elemento radice della produzione XAML.  
  
-   [Direttiva X:Class](../../../docs/framework/xaml-services/x-class-directive.md) deve essere fornito per l'elemento radice padre.  
  
-   Inserire il codice all'interno di `x:Code` verrà considerato dalla compilazione per essere all'interno dell'ambito della classe parziale che è già creata per la pagina XAML. È pertanto necessario tutto il codice che definire i membri o le variabili di tale classe parziale.  
  
-   Non è possibile definire ulteriori classi, diverso dall'annidamento di una classe all'interno della classe parziale (è consentito l'annidamento, ma non è tipico perché le classi nidificate non possono fare riferimento in XAML). Spazi dei nomi CLR nomi diverso da quello utilizzato per la classe parziale esistente non può essere definito o aggiungere.  
  
-   I riferimenti alle entità di codice all'esterno dello spazio dei nomi CLR di classe parziale devono essere completi. Se i membri dichiarati sono gli override per i membri di classe parziale sottoponibile a override, questo deve specificato con la parola chiave override specifico della lingua. Se i membri dichiarati `x:Code` ambito in conflitto con i membri della classe parziale creata da XAML, in modo che il compilatore segnala il conflitto, il file XAML non compilato o caricato.  
  
## <a name="see-also"></a>Vedere anche  
 [Direttiva x:Class](../../../docs/framework/xaml-services/x-class-directive.md)  
 [Code-behind e XAML in WPF](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)  
 [Cenni preliminari su XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
