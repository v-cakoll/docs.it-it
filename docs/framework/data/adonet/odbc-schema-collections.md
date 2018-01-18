---
title: Raccolte di schemi ODBC
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45cfed80decc2336c5a2bacf24fd075c2b81c531
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="7a62a-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="7a62a-102">ODBC Schema Collections</span></span>
<span data-ttu-id="7a62a-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="7a62a-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="7a62a-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7a62a-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="7a62a-105">Il Driver ODBC di Microsoft SQL Server supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="7a62a-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7a62a-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7a62a-106">Tables</span></span>  
  
-   <span data-ttu-id="7a62a-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="7a62a-107">Indexes</span></span>  
  
-   <span data-ttu-id="7a62a-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-108">Columns</span></span>  
  
-   <span data-ttu-id="7a62a-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-109">Procedures</span></span>  
  
-   <span data-ttu-id="7a62a-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7a62a-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7a62a-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7a62a-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7a62a-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7a62a-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7a62a-113">Tables and Views</span></span>  
  
|<span data-ttu-id="7a62a-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-114">ColumnName</span></span>|<span data-ttu-id="7a62a-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-116">TABLE_CAT</span></span>|<span data-ttu-id="7a62a-117">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-117">String</span></span>|  
|<span data-ttu-id="7a62a-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-118">TABLE_SCHEM</span></span>|<span data-ttu-id="7a62a-119">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-119">String</span></span>|  
|<span data-ttu-id="7a62a-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-120">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-121">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-121">String</span></span>|  
|<span data-ttu-id="7a62a-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-122">TABLE_TYPE</span></span>|<span data-ttu-id="7a62a-123">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-123">String</span></span>|  
|<span data-ttu-id="7a62a-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-124">REMARKS</span></span>|<span data-ttu-id="7a62a-125">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7a62a-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="7a62a-126">Indexes</span></span>  
  
|<span data-ttu-id="7a62a-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-127">ColumnName</span></span>|<span data-ttu-id="7a62a-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-129">TABLE_CAT</span></span>|<span data-ttu-id="7a62a-130">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-130">String</span></span>|  
|<span data-ttu-id="7a62a-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-131">TABLE_SCHEM</span></span>|<span data-ttu-id="7a62a-132">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-132">String</span></span>|  
|<span data-ttu-id="7a62a-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-133">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-134">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-134">String</span></span>|  
|<span data-ttu-id="7a62a-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7a62a-135">NON_UNIQUE</span></span>|<span data-ttu-id="7a62a-136">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-136">Int16</span></span>|  
|<span data-ttu-id="7a62a-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="7a62a-138">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-138">String</span></span>|  
|<span data-ttu-id="7a62a-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-139">INDEX_NAME</span></span>|<span data-ttu-id="7a62a-140">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-140">String</span></span>|  
|<span data-ttu-id="7a62a-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-141">TYPE</span></span>|<span data-ttu-id="7a62a-142">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-142">Int16</span></span>|  
|<span data-ttu-id="7a62a-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-144">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-144">Int16</span></span>|  
|<span data-ttu-id="7a62a-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-145">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-146">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-146">String</span></span>|  
|<span data-ttu-id="7a62a-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="7a62a-147">ASC_OR_DESC</span></span>|<span data-ttu-id="7a62a-148">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-148">String</span></span>|  
|<span data-ttu-id="7a62a-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="7a62a-149">CARDINATLITY</span></span>|<span data-ttu-id="7a62a-150">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-150">Int32</span></span>|  
|<span data-ttu-id="7a62a-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="7a62a-151">PAGES</span></span>|<span data-ttu-id="7a62a-152">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-152">Int32</span></span>|  
|<span data-ttu-id="7a62a-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-153">FILTER_CONDITION</span></span>|<span data-ttu-id="7a62a-154">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-154">String</span></span>|  
|<span data-ttu-id="7a62a-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7a62a-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7a62a-156">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-156">String</span></span>|  
|<span data-ttu-id="7a62a-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-158">Byte</span><span class="sxs-lookup"><span data-stu-id="7a62a-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7a62a-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-159">Columns</span></span>  
  
|<span data-ttu-id="7a62a-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-160">ColumnName</span></span>|<span data-ttu-id="7a62a-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-162">TABLE_CAT</span></span>|<span data-ttu-id="7a62a-163">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-163">String</span></span>|  
|<span data-ttu-id="7a62a-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-164">TABLE_SCHEM</span></span>|<span data-ttu-id="7a62a-165">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-165">String</span></span>|  
|<span data-ttu-id="7a62a-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-166">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-167">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-167">String</span></span>|  
|<span data-ttu-id="7a62a-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-168">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-169">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-169">String</span></span>|  
|<span data-ttu-id="7a62a-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-170">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-171">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-171">Int16</span></span>|  
|<span data-ttu-id="7a62a-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-172">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-173">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-173">String</span></span>|  
|<span data-ttu-id="7a62a-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7a62a-174">COLUMN_SIZE</span></span>|<span data-ttu-id="7a62a-175">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-175">Int32</span></span>|  
|<span data-ttu-id="7a62a-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="7a62a-177">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-177">Int32</span></span>|  
|<span data-ttu-id="7a62a-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7a62a-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7a62a-179">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-179">Int16</span></span>|  
|<span data-ttu-id="7a62a-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7a62a-181">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-181">Int16</span></span>|  
|<span data-ttu-id="7a62a-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-182">NULLABLE</span></span>|<span data-ttu-id="7a62a-183">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-183">Int16</span></span>|  
|<span data-ttu-id="7a62a-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-184">REMARKS</span></span>|<span data-ttu-id="7a62a-185">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-185">String</span></span>|  
|<span data-ttu-id="7a62a-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7a62a-186">COLUMN_DEF</span></span>|<span data-ttu-id="7a62a-187">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-187">String</span></span>|  
|<span data-ttu-id="7a62a-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-189">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-189">Int16</span></span>|  
|<span data-ttu-id="7a62a-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7a62a-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7a62a-191">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-191">Int16</span></span>|  
|<span data-ttu-id="7a62a-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7a62a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-193">Int32</span></span>|  
|<span data-ttu-id="7a62a-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-195">Int32</span></span>|  
|<span data-ttu-id="7a62a-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-196">IS_NULLABLE</span></span>|<span data-ttu-id="7a62a-197">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-197">String</span></span>|  
|<span data-ttu-id="7a62a-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7a62a-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7a62a-199">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-199">String</span></span>|  
|<span data-ttu-id="7a62a-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7a62a-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7a62a-201">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-201">String</span></span>|  
|<span data-ttu-id="7a62a-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-203">Byte</span><span class="sxs-lookup"><span data-stu-id="7a62a-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7a62a-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-204">Procedures</span></span>  
  
|<span data-ttu-id="7a62a-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-205">ColumnName</span></span>|<span data-ttu-id="7a62a-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="7a62a-208">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-208">String</span></span>|  
|<span data-ttu-id="7a62a-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7a62a-210">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-210">String</span></span>|  
|<span data-ttu-id="7a62a-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-212">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-212">String</span></span>|  
|<span data-ttu-id="7a62a-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-214">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-214">Int32</span></span>|  
|<span data-ttu-id="7a62a-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-216">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-216">Int32</span></span>|  
|<span data-ttu-id="7a62a-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7a62a-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7a62a-218">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-218">Int32</span></span>|  
|<span data-ttu-id="7a62a-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-219">REMARKS</span></span>|<span data-ttu-id="7a62a-220">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-220">String</span></span>|  
|<span data-ttu-id="7a62a-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7a62a-222">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7a62a-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7a62a-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-224">ColumnName</span></span>|<span data-ttu-id="7a62a-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="7a62a-227">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-227">String</span></span>|  
|<span data-ttu-id="7a62a-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7a62a-229">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-229">String</span></span>|  
|<span data-ttu-id="7a62a-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-231">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-231">String</span></span>|  
|<span data-ttu-id="7a62a-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-232">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-233">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-233">String</span></span>|  
|<span data-ttu-id="7a62a-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-234">COLUMN_TYPE</span></span>|<span data-ttu-id="7a62a-235">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-235">Int16</span></span>|  
|<span data-ttu-id="7a62a-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-236">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-237">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-237">Int16</span></span>|  
|<span data-ttu-id="7a62a-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-238">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-239">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-239">String</span></span>|  
|<span data-ttu-id="7a62a-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7a62a-240">COLUMN_SIZE</span></span>|<span data-ttu-id="7a62a-241">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-241">Int32</span></span>|  
|<span data-ttu-id="7a62a-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="7a62a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-243">Int32</span></span>|  
|<span data-ttu-id="7a62a-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7a62a-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7a62a-245">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-245">Int16</span></span>|  
|<span data-ttu-id="7a62a-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7a62a-247">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-247">Int16</span></span>|  
|<span data-ttu-id="7a62a-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-248">NULLABLE</span></span>|<span data-ttu-id="7a62a-249">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-249">Int16</span></span>|  
|<span data-ttu-id="7a62a-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-250">REMARKS</span></span>|<span data-ttu-id="7a62a-251">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-251">String</span></span>|  
|<span data-ttu-id="7a62a-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7a62a-252">COLUMN_DEF</span></span>|<span data-ttu-id="7a62a-253">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-253">String</span></span>|  
|<span data-ttu-id="7a62a-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-255">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-255">Int16</span></span>|  
|<span data-ttu-id="7a62a-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7a62a-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7a62a-257">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-257">Int16</span></span>|  
|<span data-ttu-id="7a62a-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7a62a-259">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-259">Int32</span></span>|  
|<span data-ttu-id="7a62a-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-261">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-261">Int32</span></span>|  
|<span data-ttu-id="7a62a-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-262">IS_NULLABLE</span></span>|<span data-ttu-id="7a62a-263">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-263">String</span></span>|  
|<span data-ttu-id="7a62a-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7a62a-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7a62a-265">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-265">String</span></span>|  
|<span data-ttu-id="7a62a-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7a62a-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7a62a-267">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-267">String</span></span>|  
|<span data-ttu-id="7a62a-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-269">Byte</span><span class="sxs-lookup"><span data-stu-id="7a62a-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7a62a-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7a62a-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7a62a-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-271">ColumnName</span></span>|<span data-ttu-id="7a62a-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="7a62a-274">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-274">String</span></span>|  
|<span data-ttu-id="7a62a-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7a62a-276">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-276">String</span></span>|  
|<span data-ttu-id="7a62a-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-278">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-278">String</span></span>|  
|<span data-ttu-id="7a62a-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-279">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-280">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-280">String</span></span>|  
|<span data-ttu-id="7a62a-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-281">COLUMN_TYPE</span></span>|<span data-ttu-id="7a62a-282">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-282">Int16</span></span>|  
|<span data-ttu-id="7a62a-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-283">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-284">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-284">Int16</span></span>|  
|<span data-ttu-id="7a62a-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-285">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-286">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-286">String</span></span>|  
|<span data-ttu-id="7a62a-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7a62a-287">COLUMN_SIZE</span></span>|<span data-ttu-id="7a62a-288">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-288">Int32</span></span>|  
|<span data-ttu-id="7a62a-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="7a62a-290">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-290">Int32</span></span>|  
|<span data-ttu-id="7a62a-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7a62a-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7a62a-292">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-292">Int16</span></span>|  
|<span data-ttu-id="7a62a-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7a62a-294">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-294">Int16</span></span>|  
|<span data-ttu-id="7a62a-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-295">NULLABLE</span></span>|<span data-ttu-id="7a62a-296">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-296">Int16</span></span>|  
|<span data-ttu-id="7a62a-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-297">REMARKS</span></span>|<span data-ttu-id="7a62a-298">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-298">String</span></span>|  
|<span data-ttu-id="7a62a-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7a62a-299">COLUMN_DEF</span></span>|<span data-ttu-id="7a62a-300">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-300">String</span></span>|  
|<span data-ttu-id="7a62a-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-302">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-302">Int16</span></span>|  
|<span data-ttu-id="7a62a-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7a62a-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7a62a-304">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-304">Int16</span></span>|  
|<span data-ttu-id="7a62a-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7a62a-306">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-306">Int32</span></span>|  
|<span data-ttu-id="7a62a-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-308">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-308">Int32</span></span>|  
|<span data-ttu-id="7a62a-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-309">IS_NULLABLE</span></span>|<span data-ttu-id="7a62a-310">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-310">String</span></span>|  
|<span data-ttu-id="7a62a-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7a62a-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7a62a-312">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-312">String</span></span>|  
|<span data-ttu-id="7a62a-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7a62a-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7a62a-314">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-314">String</span></span>|  
|<span data-ttu-id="7a62a-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-316">Byte</span><span class="sxs-lookup"><span data-stu-id="7a62a-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="7a62a-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="7a62a-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="7a62a-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le raccolte di schemi specifici seguenti oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="7a62a-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7a62a-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7a62a-319">Tables</span></span>  
  
-   <span data-ttu-id="7a62a-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-320">Columns</span></span>  
  
-   <span data-ttu-id="7a62a-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-321">Procedures</span></span>  
  
-   <span data-ttu-id="7a62a-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7a62a-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7a62a-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7a62a-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7a62a-324">Views</span></span>  
  
-   <span data-ttu-id="7a62a-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="7a62a-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7a62a-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7a62a-326">Tables and Views</span></span>  
  
|<span data-ttu-id="7a62a-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-327">ColumnName</span></span>|<span data-ttu-id="7a62a-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-330">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-330">String</span></span>|  
|<span data-ttu-id="7a62a-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-331">TABLE_OWNER</span></span>|<span data-ttu-id="7a62a-332">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-332">String</span></span>|  
|<span data-ttu-id="7a62a-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-333">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-334">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-334">String</span></span>|  
|<span data-ttu-id="7a62a-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-335">TABLE_TYPE</span></span>|<span data-ttu-id="7a62a-336">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-336">String</span></span>|  
|<span data-ttu-id="7a62a-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-337">REMARKS</span></span>|<span data-ttu-id="7a62a-338">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7a62a-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-339">Columns</span></span>  
  
|<span data-ttu-id="7a62a-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-340">ColumnName</span></span>|<span data-ttu-id="7a62a-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-343">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-343">String</span></span>|  
|<span data-ttu-id="7a62a-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-344">TABLE_OWNER</span></span>|<span data-ttu-id="7a62a-345">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-345">String</span></span>|  
|<span data-ttu-id="7a62a-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-346">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-347">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-347">String</span></span>|  
|<span data-ttu-id="7a62a-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-348">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-349">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-349">String</span></span>|  
|<span data-ttu-id="7a62a-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-350">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-351">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-351">Int16</span></span>|  
|<span data-ttu-id="7a62a-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-352">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-353">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-353">String</span></span>|  
|<span data-ttu-id="7a62a-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7a62a-354">PRECISION</span></span>|<span data-ttu-id="7a62a-355">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-355">Int32</span></span>|  
|<span data-ttu-id="7a62a-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-356">LENGTH</span></span>|<span data-ttu-id="7a62a-357">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-357">Int32</span></span>|  
|<span data-ttu-id="7a62a-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="7a62a-358">SCALE</span></span>|<span data-ttu-id="7a62a-359">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-359">Int16</span></span>|  
|<span data-ttu-id="7a62a-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-360">RADIX</span></span>|<span data-ttu-id="7a62a-361">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-361">Int16</span></span>|  
|<span data-ttu-id="7a62a-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-362">NULLABLE</span></span>|<span data-ttu-id="7a62a-363">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-363">Int16</span></span>|  
|<span data-ttu-id="7a62a-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-364">REMARKS</span></span>|<span data-ttu-id="7a62a-365">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-365">String</span></span>|  
|<span data-ttu-id="7a62a-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-367">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7a62a-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-368">Procedures</span></span>  
  
|<span data-ttu-id="7a62a-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-369">ColumnName</span></span>|<span data-ttu-id="7a62a-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-372">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-372">String</span></span>|  
|<span data-ttu-id="7a62a-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7a62a-374">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-374">String</span></span>|  
|<span data-ttu-id="7a62a-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-376">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-376">String</span></span>|  
|<span data-ttu-id="7a62a-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-378">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-378">Int16</span></span>|  
|<span data-ttu-id="7a62a-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-380">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-380">Int16</span></span>|  
|<span data-ttu-id="7a62a-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7a62a-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7a62a-382">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-382">Int16</span></span>|  
|<span data-ttu-id="7a62a-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-383">REMARKS</span></span>|<span data-ttu-id="7a62a-384">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-384">String</span></span>|  
|<span data-ttu-id="7a62a-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7a62a-386">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7a62a-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7a62a-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-388">ColumnName</span></span>|<span data-ttu-id="7a62a-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-391">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-391">String</span></span>|  
|<span data-ttu-id="7a62a-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7a62a-393">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-393">String</span></span>|  
|<span data-ttu-id="7a62a-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-395">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-395">String</span></span>|  
|<span data-ttu-id="7a62a-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-396">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-397">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-397">String</span></span>|  
|<span data-ttu-id="7a62a-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-398">COLUMN_TYPE</span></span>|<span data-ttu-id="7a62a-399">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-399">Int16</span></span>|  
|<span data-ttu-id="7a62a-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-400">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-401">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-401">Int16</span></span>|  
|<span data-ttu-id="7a62a-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-402">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-403">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-403">String</span></span>|  
|<span data-ttu-id="7a62a-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7a62a-404">PRECISION</span></span>|<span data-ttu-id="7a62a-405">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-405">Int32</span></span>|  
|<span data-ttu-id="7a62a-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-406">LENGTH</span></span>|<span data-ttu-id="7a62a-407">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-407">Int32</span></span>|  
|<span data-ttu-id="7a62a-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="7a62a-408">SCALE</span></span>|<span data-ttu-id="7a62a-409">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-409">Int16</span></span>|  
|<span data-ttu-id="7a62a-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-410">RADIX</span></span>|<span data-ttu-id="7a62a-411">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-411">Int16</span></span>|  
|<span data-ttu-id="7a62a-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-412">NULLABLE</span></span>|<span data-ttu-id="7a62a-413">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-413">Int16</span></span>|  
|<span data-ttu-id="7a62a-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-414">REMARKS</span></span>|<span data-ttu-id="7a62a-415">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-415">String</span></span>|  
|<span data-ttu-id="7a62a-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7a62a-416">OVERLOAD</span></span>|<span data-ttu-id="7a62a-417">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-417">Int32</span></span>|  
|<span data-ttu-id="7a62a-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-419">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="7a62a-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="7a62a-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="7a62a-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="7a62a-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7a62a-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7a62a-422">Tables</span></span>  
  
-   <span data-ttu-id="7a62a-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="7a62a-423">Indexes</span></span>  
  
-   <span data-ttu-id="7a62a-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-424">Columns</span></span>  
  
-   <span data-ttu-id="7a62a-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-425">Procedures</span></span>  
  
-   <span data-ttu-id="7a62a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7a62a-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7a62a-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7a62a-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7a62a-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7a62a-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7a62a-429">Tables and Views</span></span>  
  
|<span data-ttu-id="7a62a-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-430">ColumnName</span></span>|<span data-ttu-id="7a62a-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-433">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-433">String</span></span>|  
|<span data-ttu-id="7a62a-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-434">TABLE_OWNER</span></span>|<span data-ttu-id="7a62a-435">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-435">String</span></span>|  
|<span data-ttu-id="7a62a-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-436">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-437">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-437">String</span></span>|  
|<span data-ttu-id="7a62a-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-438">TABLE_TYPE</span></span>|<span data-ttu-id="7a62a-439">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-439">String</span></span>|  
|<span data-ttu-id="7a62a-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-440">REMARKS</span></span>|<span data-ttu-id="7a62a-441">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7a62a-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="7a62a-442">Columns</span></span>  
  
|<span data-ttu-id="7a62a-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-443">ColumnName</span></span>|<span data-ttu-id="7a62a-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-446">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-446">String</span></span>|  
|<span data-ttu-id="7a62a-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-447">TABLE_OWNER</span></span>|<span data-ttu-id="7a62a-448">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-448">String</span></span>|  
|<span data-ttu-id="7a62a-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-449">TABLE_NAME</span></span>|<span data-ttu-id="7a62a-450">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-450">String</span></span>|  
|<span data-ttu-id="7a62a-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-451">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-452">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-452">String</span></span>|  
|<span data-ttu-id="7a62a-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-453">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-454">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-454">Int16</span></span>|  
|<span data-ttu-id="7a62a-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-455">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-456">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-456">String</span></span>|  
|<span data-ttu-id="7a62a-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7a62a-457">PRECISION</span></span>|<span data-ttu-id="7a62a-458">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-458">Int32</span></span>|  
|<span data-ttu-id="7a62a-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-459">LENGTH</span></span>|<span data-ttu-id="7a62a-460">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-460">Int32</span></span>|  
|<span data-ttu-id="7a62a-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="7a62a-461">SCALE</span></span>|<span data-ttu-id="7a62a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-462">Int16</span></span>|  
|<span data-ttu-id="7a62a-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-463">RADIX</span></span>|<span data-ttu-id="7a62a-464">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-464">Int16</span></span>|  
|<span data-ttu-id="7a62a-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-465">NULLABLE</span></span>|<span data-ttu-id="7a62a-466">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-466">Int16</span></span>|  
|<span data-ttu-id="7a62a-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-467">REMARKS</span></span>|<span data-ttu-id="7a62a-468">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-468">String</span></span>|  
|<span data-ttu-id="7a62a-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-470">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7a62a-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="7a62a-471">Procedures</span></span>  
  
|<span data-ttu-id="7a62a-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-472">ColumnName</span></span>|<span data-ttu-id="7a62a-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-475">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-475">String</span></span>|  
|<span data-ttu-id="7a62a-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7a62a-477">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-477">String</span></span>|  
|<span data-ttu-id="7a62a-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-479">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-479">String</span></span>|  
|<span data-ttu-id="7a62a-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-481">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-481">Int16</span></span>|  
|<span data-ttu-id="7a62a-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7a62a-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7a62a-483">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-483">Int16</span></span>|  
|<span data-ttu-id="7a62a-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7a62a-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7a62a-485">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-485">Int16</span></span>|  
|<span data-ttu-id="7a62a-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-486">REMARKS</span></span>|<span data-ttu-id="7a62a-487">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-487">String</span></span>|  
|<span data-ttu-id="7a62a-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7a62a-489">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7a62a-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7a62a-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7a62a-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-491">ColumnName</span></span>|<span data-ttu-id="7a62a-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7a62a-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7a62a-494">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-494">String</span></span>|  
|<span data-ttu-id="7a62a-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7a62a-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7a62a-496">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-496">String</span></span>|  
|<span data-ttu-id="7a62a-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-498">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-498">String</span></span>|  
|<span data-ttu-id="7a62a-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-499">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-500">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-500">String</span></span>|  
|<span data-ttu-id="7a62a-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-501">COLUMN_TYPE</span></span>|<span data-ttu-id="7a62a-502">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-502">Int16</span></span>|  
|<span data-ttu-id="7a62a-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-503">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-504">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-504">Int16</span></span>|  
|<span data-ttu-id="7a62a-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-505">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-506">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-506">String</span></span>|  
|<span data-ttu-id="7a62a-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7a62a-507">PRECISION</span></span>|<span data-ttu-id="7a62a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-508">Int32</span></span>|  
|<span data-ttu-id="7a62a-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-509">LENGTH</span></span>|<span data-ttu-id="7a62a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-510">Int32</span></span>|  
|<span data-ttu-id="7a62a-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="7a62a-511">SCALE</span></span>|<span data-ttu-id="7a62a-512">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-512">Int16</span></span>|  
|<span data-ttu-id="7a62a-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-513">RADIX</span></span>|<span data-ttu-id="7a62a-514">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-514">Int16</span></span>|  
|<span data-ttu-id="7a62a-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-515">NULLABLE</span></span>|<span data-ttu-id="7a62a-516">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-516">Int16</span></span>|  
|<span data-ttu-id="7a62a-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-517">REMARKS</span></span>|<span data-ttu-id="7a62a-518">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-518">String</span></span>|  
|<span data-ttu-id="7a62a-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7a62a-519">OVERLOAD</span></span>|<span data-ttu-id="7a62a-520">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-520">Int32</span></span>|  
|<span data-ttu-id="7a62a-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-522">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7a62a-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7a62a-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7a62a-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7a62a-524">ColumnName</span></span>|<span data-ttu-id="7a62a-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7a62a-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7a62a-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="7a62a-527">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-527">String</span></span>|  
|<span data-ttu-id="7a62a-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7a62a-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7a62a-529">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-529">String</span></span>|  
|<span data-ttu-id="7a62a-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="7a62a-531">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-531">String</span></span>|  
|<span data-ttu-id="7a62a-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-532">COLUMN_NAME</span></span>|<span data-ttu-id="7a62a-533">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-533">String</span></span>|  
|<span data-ttu-id="7a62a-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-534">COLUMN_TYPE</span></span>|<span data-ttu-id="7a62a-535">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-535">Int16</span></span>|  
|<span data-ttu-id="7a62a-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-536">DATA_TYPE</span></span>|<span data-ttu-id="7a62a-537">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-537">Int16</span></span>|  
|<span data-ttu-id="7a62a-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7a62a-538">TYPE_NAME</span></span>|<span data-ttu-id="7a62a-539">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-539">String</span></span>|  
|<span data-ttu-id="7a62a-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7a62a-540">COLUMN_SIZE</span></span>|<span data-ttu-id="7a62a-541">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-541">Int32</span></span>|  
|<span data-ttu-id="7a62a-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="7a62a-543">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-543">Int32</span></span>|  
|<span data-ttu-id="7a62a-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7a62a-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7a62a-545">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-545">Int16</span></span>|  
|<span data-ttu-id="7a62a-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7a62a-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7a62a-547">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-547">Int16</span></span>|  
|<span data-ttu-id="7a62a-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-548">NULLABLE</span></span>|<span data-ttu-id="7a62a-549">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-549">Int16</span></span>|  
|<span data-ttu-id="7a62a-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7a62a-550">REMARKS</span></span>|<span data-ttu-id="7a62a-551">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-551">String</span></span>|  
|<span data-ttu-id="7a62a-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7a62a-552">COLUMN_DEF</span></span>|<span data-ttu-id="7a62a-553">String</span><span class="sxs-lookup"><span data-stu-id="7a62a-553">String</span></span>|  
|<span data-ttu-id="7a62a-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7a62a-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7a62a-555">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-555">Int16</span></span>|  
|<span data-ttu-id="7a62a-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7a62a-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7a62a-557">Int16</span><span class="sxs-lookup"><span data-stu-id="7a62a-557">Int16</span></span>|  
|<span data-ttu-id="7a62a-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7a62a-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7a62a-559">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-559">Int32</span></span>|  
|<span data-ttu-id="7a62a-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7a62a-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="7a62a-561">Int32</span><span class="sxs-lookup"><span data-stu-id="7a62a-561">Int32</span></span>|  
|<span data-ttu-id="7a62a-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7a62a-562">IS_NULLABLE</span></span>|<span data-ttu-id="7a62a-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="7a62a-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a62a-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a62a-564">See Also</span></span>  
 [<span data-ttu-id="7a62a-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7a62a-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
