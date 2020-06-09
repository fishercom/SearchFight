# SearchFight

SearchFight is a C# program for compare search results.

## Configuration

Modify configuration file Configuration.xml.

```bash
<SearchRunners>
    <SearchRunner xsi:type="WebClientSearchRunner" Name="bing" Address="https://www.bing.com/search" QueryName="q" Disabled="false">
      <Finder xsi:type="RegexResultFinder" GroupIndex="1">
        <Pattern>\&lt;span[^\&gt;]+class="sb_count"[^\&gt;]*\&gt;([\d\.\,]+)</Pattern>
      </Finder>
    </SearchRunner>
    <SearchRunner xsi:type="WebClientSearchRunner" Name="google" Address="https://www.googleapis.com/customsearch/v1" QueryName="q" Disabled="false">
      <Parameters>
        <Item Name="key" Value="AIzaSyCJzG_j-znb-OjuOP-hwfkKcjdadbMjQ4k" />
        <Item Name="cx" Value="010964284993202128394:5_v0vehmo2e" />
        <Item Name="alt" Value="json" />
      </Parameters>
      <Finder xsi:type="JSONResultFinder">
        <Path>["searchInformation"].["totalResults"]</Path>
      </Finder>
    </SearchRunner>
</SearchRunners>
```

## Usage

Use Microsoft .net Command Line.

```bash
SearchFight\bin\Release>SearchFight.exe .net java
```
