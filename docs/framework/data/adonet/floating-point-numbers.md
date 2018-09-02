---
title: Numeri a virgola mobile
ms.date: 03/30/2017
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
ms.openlocfilehash: 2ab583a07c78cfa06ac597c369486f89e19ca66e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466091"
---
# <a name="floating-point-numbers"></a>Numeri a virgola mobile
In questo argomento vengono descritti alcuni dei problemi rilevati di frequente dagli sviluppatori con l'uso di numeri a virgola mobile in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Questi problemi sono causati dal modo che i computer archiviano numeri a virgola mobile e non sono specifici di un determinato provider, ad esempio <xref:System.Data.SqlClient> o <xref:System.Data.OracleClient>.  
  
 I numeri a virgola mobile in genere non hanno una rappresentazione binaria esatta Al contrario, il computer archivia un'approssimazione del numero. In momenti differenti è possibile che vengano usati numeri diversi di cifre binarie per rappresentare il numero. Quando un numero a virgola mobile viene convertito da una rappresentazione a un'altra, le cifre meno significative di tale numero possono variare leggermente. La conversione si verifica un genere quando viene eseguito il cast di un numero da un tipo a un altro. La variazione si verifica se la conversione avviene all'interno di un database, tra tipi che rappresentano valori del database oppure tra tipi. A causa di queste modifiche, i numeri che logicamente sarebbero uguali potrebbero presentare modifiche nelle cifre meno significative, generando in questo modo valori diversi. Il numero di cifre di precisione nel numero può essere maggiore o minore del previsto. Quando viene formattato come stringa, il numero potrebbe non presentare il valore previsto.  
  
 Per minimizzare questi effetti, è necessario usare la corrispondenza più vicina disponibile tra tipi numerici. Ad esempio, se si lavora con SQL Server, il valore numerico esatto può cambiare se si converte un valore di Transact-SQL di tipo reale in un valore di tipo float. Nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], la conversione una <xref:System.Single> a un <xref:System.Double> può anche produrre risultati imprevisti. In entrambi questi casi, una strategia efficace consiste nel fare in modo che tutti i valori dell'applicazione utilizzino lo stesso tipo numerico. È anche possibile usare un tipo decimale a precisione fissa o eseguire il cast dei numeri a virgola mobile in un tipo decimale a precisione fissa prima di usarli.  
  
 Per risolvere i problemi con il confronto di uguaglianza, è consigliabile scrivere il codice dell'applicazione in modo che le variazioni delle cifre meno significative vengano ignorate. Ad esempio, anziché eseguire un confronto per verificare l'uguaglianza tra due numeri, sottrarre un numero dall'altro. Se la differenza rientra in un margine accettabile di arrotondamento, l'applicazione può considerare i numeri come se fossero identici.  
  
## <a name="see-also"></a>Vedere anche  
 [Causa della possibile perdita di precisione dei numeri a virgola mobile](https://msdn.microsoft.com/library/1acb1add-ac06-4134-a2fd-aff13d8c4c15)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
