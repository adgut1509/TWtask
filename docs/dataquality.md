---
id: dataquality
title: "Suggested Data Quality Rules"
sidebar_position: 2
---
# Suggested Data Quality Rules

Po wejściu w szczegóły kolumny, w zakładce Data Quality, użytkownicy mogą zobaczyć sugerowane reguły, które nasz system proponuje automatycznie – na podstawie nazw kolumn i ich dopasowania do znanych wzorców.

wyjaśnia użytkownikowi, czym są te sugestie i skąd się biorą,

Żeby to zrobić...

![A suggested data quality rule example](data_quality_rule_suggestion_example.png)

Dodatkowo mamy też miejsce, w którym możemy zobaczyć zbiorcze sugestie reguł dla wszystkich obiektów:

Znajdziesz je wchodząc w Data Governance → Data Quality, a następnie klikając zakładkę Suggestions

![Suggested data quality rules for objects view](suggested_data_quality_rules_for_objects.png)

![](.png)

## Examples

pokazuje kilka przykładów typowych kolumn i reguł, które mogą się pojawić jako sugestie,

<table>
  <thead>
    <tr>
      <th>Category</th>
      <th>Column Name Notes</th>
      <th>Suggested Rules</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>📧 Email</td>
      <td>Contains <code>%mail%</code></td>
      <td>Valid email address</td>
    </tr>
    <tr>
      <td>🪪 Government IDs</td>
      <td>For example: <code>%ssn%</code>, <code>%nip%</code>, <code>%pesel%</code>, <code>%ein%</code></td>
      <td>
        <ul>
          <li>Valid US SSN (for ssn, ssn_%, or %_ssn)</li>
          <li>Valid Polish NIP (for nip, %nip%, or nip%)</li>
          <li>Valid Polish PESEL (for pesel)</li>
          <li>Valid US EIN (for ein)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>📅 Dates</td>
      <td>Contains: <code>created_at</code>, <code>updated_at</code>, <code>timestamp</code>, <code>expiry_date</code></td>
      <td>
        <ul>
          <li>Future dates exist (e.g., for <code>%expiry%date%</code>)</li>
          <li>Not in future (e.g., for <code>%created%at%</code> or <code>%modified%at%</code>)</li>
          <li>Is fresh (e.g., for <code>%last%updated%</code>)</li>
          <li>No suspicious dates (for all dates)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>🌐 URLs and IPs</td>
      <td>Contains: <code>url</code>, <code>website</code>, <code>link</code>, <code>ip_address</code></td>
      <td>
        <ul>
          <li>Valid HTTP address</li>
          <li>Valid IPv4 address (for IDs)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>🌍 Postal codes</td>
      <td>Contains <code>zip_code</code></td>
      <td>Valid US zip code (depends on the country)</td>
    </tr>
    <tr>
      <td>🔢 Identifiers and product codes</td>
      <td>For example: <code>asin</code>, <code>iban</code>, <code>imei</code>, <code>vin</code>, <code>cusip</code>, <code>duns</code></td>
      <td>
        <ul>
          <li>Valid ASIN (for asin)</li>
          <li>Valid IBAN (for iban)</li>
          <li>Valid IMEI (for imei)</li>
          <li>Valid VIN (for vin)</li>
          <li>Valid CUSIP (for cusip)</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>🧾 JSON or metadata</td>
      <td>Contains: <code>%json%</code>, <code>%payload%</code></td>
      <td>Valid JSON</td>
    </tr>
  </tbody>
</table>

:::info
Nie wszystkie kolumny mają dostępne sugestie – ale w wielu przypadkach będą one przyspieszały ten manualny proces. 
:::