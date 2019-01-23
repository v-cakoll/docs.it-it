---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 072a9cd365031cd5660d1824bc229d459abc5af8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525833"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="7fbdd-102">Raccolte di schemi ODBC</span><span class="sxs-lookup"><span data-stu-id="7fbdd-102">ODBC Schema Collections</span></span>
<span data-ttu-id="7fbdd-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="7fbdd-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="7fbdd-104">Driver ODBC di Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fbdd-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="7fbdd-105">Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="7fbdd-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7fbdd-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7fbdd-106">Tables</span></span>  
  
-   <span data-ttu-id="7fbdd-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="7fbdd-107">Indexes</span></span>  
  
-   <span data-ttu-id="7fbdd-108">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-108">Columns</span></span>  
  
-   <span data-ttu-id="7fbdd-109">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-109">Procedures</span></span>  
  
-   <span data-ttu-id="7fbdd-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7fbdd-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7fbdd-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7fbdd-112">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7fbdd-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7fbdd-113">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7fbdd-113">Tables and Views</span></span>  
  
|<span data-ttu-id="7fbdd-114">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-114">ColumnName</span></span>|<span data-ttu-id="7fbdd-115">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-116">TABLE_CAT</span></span>|<span data-ttu-id="7fbdd-117">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-117">String</span></span>|  
|<span data-ttu-id="7fbdd-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-118">TABLE_SCHEM</span></span>|<span data-ttu-id="7fbdd-119">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-119">String</span></span>|  
|<span data-ttu-id="7fbdd-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-120">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-121">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-121">String</span></span>|  
|<span data-ttu-id="7fbdd-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-122">TABLE_TYPE</span></span>|<span data-ttu-id="7fbdd-123">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-123">String</span></span>|  
|<span data-ttu-id="7fbdd-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-124">REMARKS</span></span>|<span data-ttu-id="7fbdd-125">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7fbdd-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="7fbdd-126">Indexes</span></span>  
  
|<span data-ttu-id="7fbdd-127">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-127">ColumnName</span></span>|<span data-ttu-id="7fbdd-128">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-129">TABLE_CAT</span></span>|<span data-ttu-id="7fbdd-130">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-130">String</span></span>|  
|<span data-ttu-id="7fbdd-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-131">TABLE_SCHEM</span></span>|<span data-ttu-id="7fbdd-132">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-132">String</span></span>|  
|<span data-ttu-id="7fbdd-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-133">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-134">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-134">String</span></span>|  
|<span data-ttu-id="7fbdd-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-135">NON_UNIQUE</span></span>|<span data-ttu-id="7fbdd-136">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-136">Int16</span></span>|  
|<span data-ttu-id="7fbdd-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-138">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-138">String</span></span>|  
|<span data-ttu-id="7fbdd-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-139">INDEX_NAME</span></span>|<span data-ttu-id="7fbdd-140">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-140">String</span></span>|  
|<span data-ttu-id="7fbdd-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-141">TYPE</span></span>|<span data-ttu-id="7fbdd-142">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-142">Int16</span></span>|  
|<span data-ttu-id="7fbdd-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-144">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-144">Int16</span></span>|  
|<span data-ttu-id="7fbdd-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-145">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-146">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-146">String</span></span>|  
|<span data-ttu-id="7fbdd-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="7fbdd-147">ASC_OR_DESC</span></span>|<span data-ttu-id="7fbdd-148">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-148">String</span></span>|  
|<span data-ttu-id="7fbdd-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="7fbdd-149">CARDINATLITY</span></span>|<span data-ttu-id="7fbdd-150">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-150">Int32</span></span>|  
|<span data-ttu-id="7fbdd-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="7fbdd-151">PAGES</span></span>|<span data-ttu-id="7fbdd-152">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-152">Int32</span></span>|  
|<span data-ttu-id="7fbdd-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-153">FILTER_CONDITION</span></span>|<span data-ttu-id="7fbdd-154">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-154">String</span></span>|  
|<span data-ttu-id="7fbdd-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7fbdd-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7fbdd-156">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-156">String</span></span>|  
|<span data-ttu-id="7fbdd-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-158">Byte</span><span class="sxs-lookup"><span data-stu-id="7fbdd-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7fbdd-159">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-159">Columns</span></span>  
  
|<span data-ttu-id="7fbdd-160">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-160">ColumnName</span></span>|<span data-ttu-id="7fbdd-161">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-162">TABLE_CAT</span></span>|<span data-ttu-id="7fbdd-163">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-163">String</span></span>|  
|<span data-ttu-id="7fbdd-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-164">TABLE_SCHEM</span></span>|<span data-ttu-id="7fbdd-165">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-165">String</span></span>|  
|<span data-ttu-id="7fbdd-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-166">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-167">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-167">String</span></span>|  
|<span data-ttu-id="7fbdd-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-168">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-169">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-169">String</span></span>|  
|<span data-ttu-id="7fbdd-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-170">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-171">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-171">Int16</span></span>|  
|<span data-ttu-id="7fbdd-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-172">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-173">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-173">String</span></span>|  
|<span data-ttu-id="7fbdd-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-174">COLUMN_SIZE</span></span>|<span data-ttu-id="7fbdd-175">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-175">Int32</span></span>|  
|<span data-ttu-id="7fbdd-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="7fbdd-177">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-177">Int32</span></span>|  
|<span data-ttu-id="7fbdd-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7fbdd-179">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-179">Int16</span></span>|  
|<span data-ttu-id="7fbdd-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7fbdd-181">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-181">Int16</span></span>|  
|<span data-ttu-id="7fbdd-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-182">NULLABLE</span></span>|<span data-ttu-id="7fbdd-183">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-183">Int16</span></span>|  
|<span data-ttu-id="7fbdd-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-184">REMARKS</span></span>|<span data-ttu-id="7fbdd-185">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-185">String</span></span>|  
|<span data-ttu-id="7fbdd-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7fbdd-186">COLUMN_DEF</span></span>|<span data-ttu-id="7fbdd-187">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-187">String</span></span>|  
|<span data-ttu-id="7fbdd-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-189">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-189">Int16</span></span>|  
|<span data-ttu-id="7fbdd-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7fbdd-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7fbdd-191">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-191">Int16</span></span>|  
|<span data-ttu-id="7fbdd-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7fbdd-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-193">Int32</span></span>|  
|<span data-ttu-id="7fbdd-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-195">Int32</span></span>|  
|<span data-ttu-id="7fbdd-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-196">IS_NULLABLE</span></span>|<span data-ttu-id="7fbdd-197">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-197">String</span></span>|  
|<span data-ttu-id="7fbdd-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7fbdd-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7fbdd-199">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-199">String</span></span>|  
|<span data-ttu-id="7fbdd-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7fbdd-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7fbdd-201">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-201">String</span></span>|  
|<span data-ttu-id="7fbdd-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-203">Byte</span><span class="sxs-lookup"><span data-stu-id="7fbdd-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7fbdd-204">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-204">Procedures</span></span>  
  
|<span data-ttu-id="7fbdd-205">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-205">ColumnName</span></span>|<span data-ttu-id="7fbdd-206">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="7fbdd-208">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-208">String</span></span>|  
|<span data-ttu-id="7fbdd-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7fbdd-210">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-210">String</span></span>|  
|<span data-ttu-id="7fbdd-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-212">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-212">String</span></span>|  
|<span data-ttu-id="7fbdd-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-214">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-214">Int32</span></span>|  
|<span data-ttu-id="7fbdd-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-216">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-216">Int32</span></span>|  
|<span data-ttu-id="7fbdd-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7fbdd-218">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-218">Int32</span></span>|  
|<span data-ttu-id="7fbdd-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-219">REMARKS</span></span>|<span data-ttu-id="7fbdd-220">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-220">String</span></span>|  
|<span data-ttu-id="7fbdd-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7fbdd-222">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7fbdd-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7fbdd-224">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-224">ColumnName</span></span>|<span data-ttu-id="7fbdd-225">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="7fbdd-227">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-227">String</span></span>|  
|<span data-ttu-id="7fbdd-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7fbdd-229">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-229">String</span></span>|  
|<span data-ttu-id="7fbdd-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-231">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-231">String</span></span>|  
|<span data-ttu-id="7fbdd-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-232">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-233">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-233">String</span></span>|  
|<span data-ttu-id="7fbdd-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-234">COLUMN_TYPE</span></span>|<span data-ttu-id="7fbdd-235">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-235">Int16</span></span>|  
|<span data-ttu-id="7fbdd-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-236">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-237">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-237">Int16</span></span>|  
|<span data-ttu-id="7fbdd-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-238">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-239">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-239">String</span></span>|  
|<span data-ttu-id="7fbdd-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-240">COLUMN_SIZE</span></span>|<span data-ttu-id="7fbdd-241">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-241">Int32</span></span>|  
|<span data-ttu-id="7fbdd-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="7fbdd-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-243">Int32</span></span>|  
|<span data-ttu-id="7fbdd-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7fbdd-245">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-245">Int16</span></span>|  
|<span data-ttu-id="7fbdd-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7fbdd-247">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-247">Int16</span></span>|  
|<span data-ttu-id="7fbdd-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-248">NULLABLE</span></span>|<span data-ttu-id="7fbdd-249">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-249">Int16</span></span>|  
|<span data-ttu-id="7fbdd-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-250">REMARKS</span></span>|<span data-ttu-id="7fbdd-251">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-251">String</span></span>|  
|<span data-ttu-id="7fbdd-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7fbdd-252">COLUMN_DEF</span></span>|<span data-ttu-id="7fbdd-253">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-253">String</span></span>|  
|<span data-ttu-id="7fbdd-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-255">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-255">Int16</span></span>|  
|<span data-ttu-id="7fbdd-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7fbdd-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7fbdd-257">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-257">Int16</span></span>|  
|<span data-ttu-id="7fbdd-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7fbdd-259">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-259">Int32</span></span>|  
|<span data-ttu-id="7fbdd-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-261">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-261">Int32</span></span>|  
|<span data-ttu-id="7fbdd-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-262">IS_NULLABLE</span></span>|<span data-ttu-id="7fbdd-263">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-263">String</span></span>|  
|<span data-ttu-id="7fbdd-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7fbdd-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7fbdd-265">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-265">String</span></span>|  
|<span data-ttu-id="7fbdd-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7fbdd-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7fbdd-267">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-267">String</span></span>|  
|<span data-ttu-id="7fbdd-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-269">Byte</span><span class="sxs-lookup"><span data-stu-id="7fbdd-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7fbdd-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7fbdd-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7fbdd-271">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-271">ColumnName</span></span>|<span data-ttu-id="7fbdd-272">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="7fbdd-274">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-274">String</span></span>|  
|<span data-ttu-id="7fbdd-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7fbdd-276">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-276">String</span></span>|  
|<span data-ttu-id="7fbdd-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-278">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-278">String</span></span>|  
|<span data-ttu-id="7fbdd-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-279">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-280">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-280">String</span></span>|  
|<span data-ttu-id="7fbdd-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-281">COLUMN_TYPE</span></span>|<span data-ttu-id="7fbdd-282">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-282">Int16</span></span>|  
|<span data-ttu-id="7fbdd-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-283">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-284">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-284">Int16</span></span>|  
|<span data-ttu-id="7fbdd-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-285">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-286">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-286">String</span></span>|  
|<span data-ttu-id="7fbdd-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-287">COLUMN_SIZE</span></span>|<span data-ttu-id="7fbdd-288">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-288">Int32</span></span>|  
|<span data-ttu-id="7fbdd-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="7fbdd-290">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-290">Int32</span></span>|  
|<span data-ttu-id="7fbdd-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7fbdd-292">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-292">Int16</span></span>|  
|<span data-ttu-id="7fbdd-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7fbdd-294">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-294">Int16</span></span>|  
|<span data-ttu-id="7fbdd-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-295">NULLABLE</span></span>|<span data-ttu-id="7fbdd-296">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-296">Int16</span></span>|  
|<span data-ttu-id="7fbdd-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-297">REMARKS</span></span>|<span data-ttu-id="7fbdd-298">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-298">String</span></span>|  
|<span data-ttu-id="7fbdd-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7fbdd-299">COLUMN_DEF</span></span>|<span data-ttu-id="7fbdd-300">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-300">String</span></span>|  
|<span data-ttu-id="7fbdd-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-302">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-302">Int16</span></span>|  
|<span data-ttu-id="7fbdd-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7fbdd-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7fbdd-304">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-304">Int16</span></span>|  
|<span data-ttu-id="7fbdd-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7fbdd-306">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-306">Int32</span></span>|  
|<span data-ttu-id="7fbdd-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-308">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-308">Int32</span></span>|  
|<span data-ttu-id="7fbdd-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-309">IS_NULLABLE</span></span>|<span data-ttu-id="7fbdd-310">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-310">String</span></span>|  
|<span data-ttu-id="7fbdd-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7fbdd-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="7fbdd-312">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-312">String</span></span>|  
|<span data-ttu-id="7fbdd-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7fbdd-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="7fbdd-314">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-314">String</span></span>|  
|<span data-ttu-id="7fbdd-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-316">Byte</span><span class="sxs-lookup"><span data-stu-id="7fbdd-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="7fbdd-317">Driver Microsoft ODBC per Oracle</span><span class="sxs-lookup"><span data-stu-id="7fbdd-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="7fbdd-318">Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="7fbdd-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7fbdd-319">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7fbdd-319">Tables</span></span>  
  
-   <span data-ttu-id="7fbdd-320">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-320">Columns</span></span>  
  
-   <span data-ttu-id="7fbdd-321">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-321">Procedures</span></span>  
  
-   <span data-ttu-id="7fbdd-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7fbdd-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7fbdd-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7fbdd-324">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7fbdd-324">Views</span></span>  
  
-   <span data-ttu-id="7fbdd-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="7fbdd-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7fbdd-326">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7fbdd-326">Tables and Views</span></span>  
  
|<span data-ttu-id="7fbdd-327">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-327">ColumnName</span></span>|<span data-ttu-id="7fbdd-328">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-330">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-330">String</span></span>|  
|<span data-ttu-id="7fbdd-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-331">TABLE_OWNER</span></span>|<span data-ttu-id="7fbdd-332">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-332">String</span></span>|  
|<span data-ttu-id="7fbdd-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-333">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-334">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-334">String</span></span>|  
|<span data-ttu-id="7fbdd-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-335">TABLE_TYPE</span></span>|<span data-ttu-id="7fbdd-336">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-336">String</span></span>|  
|<span data-ttu-id="7fbdd-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-337">REMARKS</span></span>|<span data-ttu-id="7fbdd-338">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7fbdd-339">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-339">Columns</span></span>  
  
|<span data-ttu-id="7fbdd-340">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-340">ColumnName</span></span>|<span data-ttu-id="7fbdd-341">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-343">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-343">String</span></span>|  
|<span data-ttu-id="7fbdd-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-344">TABLE_OWNER</span></span>|<span data-ttu-id="7fbdd-345">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-345">String</span></span>|  
|<span data-ttu-id="7fbdd-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-346">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-347">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-347">String</span></span>|  
|<span data-ttu-id="7fbdd-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-348">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-349">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-349">String</span></span>|  
|<span data-ttu-id="7fbdd-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-350">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-351">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-351">Int16</span></span>|  
|<span data-ttu-id="7fbdd-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-352">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-353">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-353">String</span></span>|  
|<span data-ttu-id="7fbdd-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-354">PRECISION</span></span>|<span data-ttu-id="7fbdd-355">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-355">Int32</span></span>|  
|<span data-ttu-id="7fbdd-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-356">LENGTH</span></span>|<span data-ttu-id="7fbdd-357">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-357">Int32</span></span>|  
|<span data-ttu-id="7fbdd-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-358">SCALE</span></span>|<span data-ttu-id="7fbdd-359">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-359">Int16</span></span>|  
|<span data-ttu-id="7fbdd-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-360">RADIX</span></span>|<span data-ttu-id="7fbdd-361">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-361">Int16</span></span>|  
|<span data-ttu-id="7fbdd-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-362">NULLABLE</span></span>|<span data-ttu-id="7fbdd-363">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-363">Int16</span></span>|  
|<span data-ttu-id="7fbdd-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-364">REMARKS</span></span>|<span data-ttu-id="7fbdd-365">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-365">String</span></span>|  
|<span data-ttu-id="7fbdd-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-367">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7fbdd-368">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-368">Procedures</span></span>  
  
|<span data-ttu-id="7fbdd-369">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-369">ColumnName</span></span>|<span data-ttu-id="7fbdd-370">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-372">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-372">String</span></span>|  
|<span data-ttu-id="7fbdd-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7fbdd-374">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-374">String</span></span>|  
|<span data-ttu-id="7fbdd-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-376">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-376">String</span></span>|  
|<span data-ttu-id="7fbdd-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-378">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-378">Int16</span></span>|  
|<span data-ttu-id="7fbdd-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-380">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-380">Int16</span></span>|  
|<span data-ttu-id="7fbdd-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7fbdd-382">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-382">Int16</span></span>|  
|<span data-ttu-id="7fbdd-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-383">REMARKS</span></span>|<span data-ttu-id="7fbdd-384">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-384">String</span></span>|  
|<span data-ttu-id="7fbdd-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7fbdd-386">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7fbdd-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7fbdd-388">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-388">ColumnName</span></span>|<span data-ttu-id="7fbdd-389">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-391">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-391">String</span></span>|  
|<span data-ttu-id="7fbdd-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7fbdd-393">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-393">String</span></span>|  
|<span data-ttu-id="7fbdd-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-395">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-395">String</span></span>|  
|<span data-ttu-id="7fbdd-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-396">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-397">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-397">String</span></span>|  
|<span data-ttu-id="7fbdd-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-398">COLUMN_TYPE</span></span>|<span data-ttu-id="7fbdd-399">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-399">Int16</span></span>|  
|<span data-ttu-id="7fbdd-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-400">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-401">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-401">Int16</span></span>|  
|<span data-ttu-id="7fbdd-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-402">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-403">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-403">String</span></span>|  
|<span data-ttu-id="7fbdd-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-404">PRECISION</span></span>|<span data-ttu-id="7fbdd-405">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-405">Int32</span></span>|  
|<span data-ttu-id="7fbdd-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-406">LENGTH</span></span>|<span data-ttu-id="7fbdd-407">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-407">Int32</span></span>|  
|<span data-ttu-id="7fbdd-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-408">SCALE</span></span>|<span data-ttu-id="7fbdd-409">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-409">Int16</span></span>|  
|<span data-ttu-id="7fbdd-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-410">RADIX</span></span>|<span data-ttu-id="7fbdd-411">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-411">Int16</span></span>|  
|<span data-ttu-id="7fbdd-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-412">NULLABLE</span></span>|<span data-ttu-id="7fbdd-413">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-413">Int16</span></span>|  
|<span data-ttu-id="7fbdd-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-414">REMARKS</span></span>|<span data-ttu-id="7fbdd-415">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-415">String</span></span>|  
|<span data-ttu-id="7fbdd-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7fbdd-416">OVERLOAD</span></span>|<span data-ttu-id="7fbdd-417">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-417">Int32</span></span>|  
|<span data-ttu-id="7fbdd-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-419">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="7fbdd-420">Driver ODBC per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="7fbdd-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="7fbdd-421">Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="7fbdd-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="7fbdd-422">Tabelle</span><span class="sxs-lookup"><span data-stu-id="7fbdd-422">Tables</span></span>  
  
-   <span data-ttu-id="7fbdd-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="7fbdd-423">Indexes</span></span>  
  
-   <span data-ttu-id="7fbdd-424">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-424">Columns</span></span>  
  
-   <span data-ttu-id="7fbdd-425">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-425">Procedures</span></span>  
  
-   <span data-ttu-id="7fbdd-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="7fbdd-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7fbdd-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="7fbdd-428">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="7fbdd-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="7fbdd-429">Tables e Views</span><span class="sxs-lookup"><span data-stu-id="7fbdd-429">Tables and Views</span></span>  
  
|<span data-ttu-id="7fbdd-430">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-430">ColumnName</span></span>|<span data-ttu-id="7fbdd-431">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-433">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-433">String</span></span>|  
|<span data-ttu-id="7fbdd-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-434">TABLE_OWNER</span></span>|<span data-ttu-id="7fbdd-435">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-435">String</span></span>|  
|<span data-ttu-id="7fbdd-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-436">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-437">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-437">String</span></span>|  
|<span data-ttu-id="7fbdd-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-438">TABLE_TYPE</span></span>|<span data-ttu-id="7fbdd-439">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-439">String</span></span>|  
|<span data-ttu-id="7fbdd-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-440">REMARKS</span></span>|<span data-ttu-id="7fbdd-441">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7fbdd-442">Colonne</span><span class="sxs-lookup"><span data-stu-id="7fbdd-442">Columns</span></span>  
  
|<span data-ttu-id="7fbdd-443">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-443">ColumnName</span></span>|<span data-ttu-id="7fbdd-444">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-446">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-446">String</span></span>|  
|<span data-ttu-id="7fbdd-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-447">TABLE_OWNER</span></span>|<span data-ttu-id="7fbdd-448">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-448">String</span></span>|  
|<span data-ttu-id="7fbdd-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-449">TABLE_NAME</span></span>|<span data-ttu-id="7fbdd-450">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-450">String</span></span>|  
|<span data-ttu-id="7fbdd-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-451">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-452">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-452">String</span></span>|  
|<span data-ttu-id="7fbdd-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-453">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-454">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-454">Int16</span></span>|  
|<span data-ttu-id="7fbdd-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-455">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-456">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-456">String</span></span>|  
|<span data-ttu-id="7fbdd-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-457">PRECISION</span></span>|<span data-ttu-id="7fbdd-458">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-458">Int32</span></span>|  
|<span data-ttu-id="7fbdd-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-459">LENGTH</span></span>|<span data-ttu-id="7fbdd-460">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-460">Int32</span></span>|  
|<span data-ttu-id="7fbdd-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-461">SCALE</span></span>|<span data-ttu-id="7fbdd-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-462">Int16</span></span>|  
|<span data-ttu-id="7fbdd-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-463">RADIX</span></span>|<span data-ttu-id="7fbdd-464">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-464">Int16</span></span>|  
|<span data-ttu-id="7fbdd-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-465">NULLABLE</span></span>|<span data-ttu-id="7fbdd-466">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-466">Int16</span></span>|  
|<span data-ttu-id="7fbdd-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-467">REMARKS</span></span>|<span data-ttu-id="7fbdd-468">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-468">String</span></span>|  
|<span data-ttu-id="7fbdd-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-470">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7fbdd-471">Procedure</span><span class="sxs-lookup"><span data-stu-id="7fbdd-471">Procedures</span></span>  
  
|<span data-ttu-id="7fbdd-472">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-472">ColumnName</span></span>|<span data-ttu-id="7fbdd-473">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-475">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-475">String</span></span>|  
|<span data-ttu-id="7fbdd-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7fbdd-477">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-477">String</span></span>|  
|<span data-ttu-id="7fbdd-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-479">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-479">String</span></span>|  
|<span data-ttu-id="7fbdd-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-481">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-481">Int16</span></span>|  
|<span data-ttu-id="7fbdd-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="7fbdd-483">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-483">Int16</span></span>|  
|<span data-ttu-id="7fbdd-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="7fbdd-485">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-485">Int16</span></span>|  
|<span data-ttu-id="7fbdd-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-486">REMARKS</span></span>|<span data-ttu-id="7fbdd-487">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-487">String</span></span>|  
|<span data-ttu-id="7fbdd-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7fbdd-489">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7fbdd-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7fbdd-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7fbdd-491">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-491">ColumnName</span></span>|<span data-ttu-id="7fbdd-492">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="7fbdd-494">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-494">String</span></span>|  
|<span data-ttu-id="7fbdd-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fbdd-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="7fbdd-496">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-496">String</span></span>|  
|<span data-ttu-id="7fbdd-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-498">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-498">String</span></span>|  
|<span data-ttu-id="7fbdd-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-499">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-500">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-500">String</span></span>|  
|<span data-ttu-id="7fbdd-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-501">COLUMN_TYPE</span></span>|<span data-ttu-id="7fbdd-502">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-502">Int16</span></span>|  
|<span data-ttu-id="7fbdd-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-503">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-504">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-504">Int16</span></span>|  
|<span data-ttu-id="7fbdd-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-505">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-506">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-506">String</span></span>|  
|<span data-ttu-id="7fbdd-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-507">PRECISION</span></span>|<span data-ttu-id="7fbdd-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-508">Int32</span></span>|  
|<span data-ttu-id="7fbdd-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-509">LENGTH</span></span>|<span data-ttu-id="7fbdd-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-510">Int32</span></span>|  
|<span data-ttu-id="7fbdd-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-511">SCALE</span></span>|<span data-ttu-id="7fbdd-512">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-512">Int16</span></span>|  
|<span data-ttu-id="7fbdd-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-513">RADIX</span></span>|<span data-ttu-id="7fbdd-514">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-514">Int16</span></span>|  
|<span data-ttu-id="7fbdd-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-515">NULLABLE</span></span>|<span data-ttu-id="7fbdd-516">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-516">Int16</span></span>|  
|<span data-ttu-id="7fbdd-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-517">REMARKS</span></span>|<span data-ttu-id="7fbdd-518">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-518">String</span></span>|  
|<span data-ttu-id="7fbdd-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7fbdd-519">OVERLOAD</span></span>|<span data-ttu-id="7fbdd-520">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-520">Int32</span></span>|  
|<span data-ttu-id="7fbdd-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-522">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7fbdd-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7fbdd-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7fbdd-524">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="7fbdd-524">ColumnName</span></span>|<span data-ttu-id="7fbdd-525">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7fbdd-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="7fbdd-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="7fbdd-527">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-527">String</span></span>|  
|<span data-ttu-id="7fbdd-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="7fbdd-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="7fbdd-529">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-529">String</span></span>|  
|<span data-ttu-id="7fbdd-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="7fbdd-531">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-531">String</span></span>|  
|<span data-ttu-id="7fbdd-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-532">COLUMN_NAME</span></span>|<span data-ttu-id="7fbdd-533">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-533">String</span></span>|  
|<span data-ttu-id="7fbdd-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-534">COLUMN_TYPE</span></span>|<span data-ttu-id="7fbdd-535">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-535">Int16</span></span>|  
|<span data-ttu-id="7fbdd-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-536">DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-537">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-537">Int16</span></span>|  
|<span data-ttu-id="7fbdd-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7fbdd-538">TYPE_NAME</span></span>|<span data-ttu-id="7fbdd-539">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-539">String</span></span>|  
|<span data-ttu-id="7fbdd-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-540">COLUMN_SIZE</span></span>|<span data-ttu-id="7fbdd-541">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-541">Int32</span></span>|  
|<span data-ttu-id="7fbdd-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="7fbdd-543">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-543">Int32</span></span>|  
|<span data-ttu-id="7fbdd-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="7fbdd-545">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-545">Int16</span></span>|  
|<span data-ttu-id="7fbdd-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="7fbdd-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="7fbdd-547">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-547">Int16</span></span>|  
|<span data-ttu-id="7fbdd-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-548">NULLABLE</span></span>|<span data-ttu-id="7fbdd-549">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-549">Int16</span></span>|  
|<span data-ttu-id="7fbdd-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="7fbdd-550">REMARKS</span></span>|<span data-ttu-id="7fbdd-551">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-551">String</span></span>|  
|<span data-ttu-id="7fbdd-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="7fbdd-552">COLUMN_DEF</span></span>|<span data-ttu-id="7fbdd-553">String</span><span class="sxs-lookup"><span data-stu-id="7fbdd-553">String</span></span>|  
|<span data-ttu-id="7fbdd-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="7fbdd-555">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-555">Int16</span></span>|  
|<span data-ttu-id="7fbdd-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="7fbdd-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="7fbdd-557">Int16</span><span class="sxs-lookup"><span data-stu-id="7fbdd-557">Int16</span></span>|  
|<span data-ttu-id="7fbdd-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7fbdd-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="7fbdd-559">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-559">Int32</span></span>|  
|<span data-ttu-id="7fbdd-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7fbdd-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="7fbdd-561">Int32</span><span class="sxs-lookup"><span data-stu-id="7fbdd-561">Int32</span></span>|  
|<span data-ttu-id="7fbdd-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7fbdd-562">IS_NULLABLE</span></span>|<span data-ttu-id="7fbdd-563">Stringa</span><span class="sxs-lookup"><span data-stu-id="7fbdd-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7fbdd-564">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fbdd-564">See also</span></span>
- [<span data-ttu-id="7fbdd-565">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7fbdd-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
