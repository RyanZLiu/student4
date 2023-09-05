---
toc: true
comments: false
layout: post
title: Tennis Players
description: Some basic stats of the top 11 best male tennis players
type: hacks
courses: { compsci: {week: 2} }
---

<!-- Head contains information to Support the Document -->
<head>
    <!-- load jQuery and DataTables output style and scripts -->
    <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.13.4/css/jquery.dataTables.min.css">
    <script type="text/javascript" language="javascript" src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script>var define = null;</script>
    <script type="text/javascript" language="javascript" src="https://cdn.datatables.net/1.13.4/js/jquery.dataTables.min.js"></script>
</head>

<!-- Body contains the contents of the Document -->
<body>
    <table id="demo" class="table">
        <thead>
            <tr>
                <th>Player</th>
                <th>Age</th>
                <th>Nationality</th>
                <th>Career Earnings</th>
                <th>Ranking</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Carlos Alcaraz</td>
                <td>20</td>
                <td>Spanish</td>
                <td>$16,660,732</td>
                <td>#1</td>
            </tr>
            <tr>
                <td>Novak Djokovic</td>
                <td>36</td>
                <td>Serbian</td>
                <td>$166,860,000</td>
                <td>#2</td>
            </tr>
            <tr>
                <td>Daniil Medvedev</td>
                <td>27</td>
                <td>Russian</td>
                <td>$31,495,691</td>
                <td>#3</td>
            </tr>
            <tr>
                <td>Holger Rune</td>
                <td>20</td>
                <td>Danish</td>
                <td>$42,21,298</td>
                <td>#4</td>
            </tr>
            <tr>
                <td>Casper Ruud</td>
                <td>24</td>
                <td>Norwegian</td>
                <td>$15,411,069</td>
                <td>#5</td>
            </tr>
            <tr>
                <td>Jannik Sinner</td>
                <td>22</td>
                <td>Italian</td>
                <td>$9,633,518</td>
                <td>$6</td>
            </tr>
            <tr>
                <td>Stefanos Tsitsipas</td>
                <td>25</td>
                <td>Greek</td>
                <td>$26,739,163</td>
                <td>#7</td>
            </tr>
            <tr>
                <td>Andrey Rublev</td>
                <td>25</td>
                <td>Russian</td>
                <td>$18,497,680</td>
                <td>#8</td>
            </tr>
            <tr>
                <td>Taylor Fritz</td>
                <td>25</td>
                <td>American</td>
                <td>$11,897,055</td>
                <td>#9</td>
            </tr>
            <tr>
                <td>Frances Tiafoe</td>
                <td>25</td>
                <td>American</td>
                <td>$9,179,587</td>
                <td>#10</td>
            </tr>
            <tr>
                <td>Karen Khachanov</td>
                <td>27</td>
                <td>Russian</td>
                <td>$14,343,187</td>
                <td>#11</td>
            </tr>
        </tbody>
    </table>
</body>

<!-- Script is used to embed executable code -->
<script>
    $("#demo").DataTable();
</script>