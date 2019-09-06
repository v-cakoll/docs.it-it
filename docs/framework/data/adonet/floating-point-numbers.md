---
title: Numeri a virgola mobile
ms.date: 03/30/2017
ms.assetid: 73c218c6-1c44-4402-a167-4f6262629a91
ms.openlocfilehash: 1f76a6ab8cc2a44580229014dd8ebae6b317921f
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374422"
---
# <a name="floating-point-numbers"></a>Numeri a virgola mobile
Questo argomento descrive alcuni dei problemi che gli sviluppatori incontrano spesso quando lavorano con numeri a virgola mobile in ADO.NET. Questi problemi sono causati dal modo in cui i computer archiviano i numeri a virgola mobile e non sono specifici di un determinato <xref:System.Data.SqlClient> provider <xref:System.Data.OracleClient>, ad esempio o.  
  
 I numeri a virgola mobile in genere non hanno una rappresentazione binaria esatta Al contrario, il computer archivia un'approssimazione del numero. In momenti differenti è possibile che vengano usati numeri diversi di cifre binarie per rappresentare il numero. Quando un numero a virgola mobile viene convertito da una rappresentazione a un'altra, le cifre meno significative di tale numero possono variare leggermente. La conversione si verifica un genere quando viene eseguito il cast di un numero da un tipo a un altro. La variazione si verifica se la conversione avviene all'interno di un database, tra tipi che rappresentano valori del database oppure tra tipi. A causa di queste modifiche, i numeri che logicamente sarebbero uguali potrebbero presentare modifiche nelle cifre meno significative, generando in questo modo valori diversi. Il numero di cifre di precisione nel numero può essere maggiore o minore del previsto. Quando viene formattato come stringa, il numero potrebbe non presentare il valore previsto.  
  
 Per minimizzare questi effetti, è necessario usare la corrispondenza più vicina disponibile tra tipi numerici. Se, ad esempio, si utilizza SQL Server, il valore numerico esatto può variare se si converte un valore Transact-SQL di tipo reale in un valore di tipo float. Nella .NET Framework la conversione <xref:System.Single> di in un oggetto <xref:System.Double> può produrre risultati imprevisti. In entrambi questi casi, una strategia efficace consiste nel fare in modo che tutti i valori dell'applicazione utilizzino lo stesso tipo numerico. È anche possibile usare un tipo decimale a precisione fissa o eseguire il cast dei numeri a virgola mobile in un tipo decimale a precisione fissa prima di usarli.  
  
 Per risolvere i problemi con il confronto di uguaglianza, è consigliabile scrivere il codice dell'applicazione in modo che le variazioni delle cifre meno significative vengano ignorate. Ad esempio, anziché eseguire un confronto per verificare l'uguaglianza tra due numeri, sottrarre un numero dall'altro. Se la differenza rientra in un margine accettabile di arrotondamento, l'applicazione può considerare i numeri come se fossero identici.  
  
## <a name="see-also"></a>Vedere anche

- [Causa della possibile perdita di precisione dei numeri a virgola mobile](/cpp/build/why-floating-point-numbers-may-lose-precision)
- [Panoramica di ADO.NET](ado-net-overview.md)
