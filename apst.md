---
layout: page
title: Standards
permalink: /apst/
---

The [Australian Professional Standards for Teachers (APST)](https://www.aitsl.edu.au/docs/default-source/apst-resources/australian_professional_standard_for_teachers_final.pdf) are summarised here under their three main headings, and listed below in more detail with my reflections and evidence for each. Illustrations of these standards, as well as further details can also be found on the [Australian Institute for Teaching and School Leadership (AITSL)](https://www.aitsl.edu.au/teach/standards) website.

The following evidence is given for the graduate level proficiency.

# Professional Knowledge
### [1. Know students and how they learn](#apst1)
1. [Physical, social and intellectual development and characteristics of students](#apst1-1)
2. [Understand how students learn](#apst1-2)
3. [Students with diverse linguistic, cultural, religious and socioeconomic backgrounds](#apst1-3)
4. [Strategies for teaching Aboriginal and Torres Strait Islander students](#apst1-4)
5. [Differentiate teaching to meet the specific learning needs of students across the full range of abilities](#apst1-5)
6. [Strategies to support full participation of students with disability](#apst1-6)

### [2. Know the content and how to teach it](#apst2)
1. [Content and teaching strategies of the teaching area](#apst2-1)
2. [Content selection and organisation](#apst2-2)
3. [Curriculum, assessment and reporting](#apst2-3)
4. [Understand and respect Aboriginal and Torres Strait Islander people to promote reconciliation between Indigenous and non-Indigenous Australians](#apst2-4)
5. [Literacy and numeracy strategies](#apst2-5)
6. [Information and Communication Technology (ICT)](#apst2-6)  

# Professional Practice
### [3. Plan for and implement effective teaching and learning](#apst3)
1. [Establish challenging learning goals](#apst3-1)
2. [Plan, structure and sequence learning programs](#apst3-2)
3. [Use teaching strategies](#apst3-3)
4. [Select and use resources](#apst3-4)
5. [Use effective classroom communication](#apst3-5)
6. [Evaluate and improve teaching programs](#apst3-6)
7. [Engage parents/carers in the educative process](#apst3-7)

### [4. Create and maintain supportive and safe learning environments](#apst4)
1. [Support student participation](#apst4-1)
2. [Manage classroom activities](#apst4-2)
3. [Manage challenging behaviour](#apst4-3)
4. [Maintain student safety](#apst4-4)
5. [Use ICT safely, responsibly and ethically](#apst4-5)

### [5. Assess, provide feedback and report on student learning](#apst5)
1. [Assess student learning](#apst5-1)
2. [Provide feedback to students on their learning](#apst5-2)
3. [Make consistent and comparable judgements](#apst5-3)
4. [Interpret student data](#apst5-4)
5. [Report on student achievement](#apst5-5)

# Professional Engagement
### [6. Engage in professional learning](#apst6)
1. [Identify and plan professional learning needs](#apst6-1)
2. [Engage in professional learning and improve practice](#apst6-2)
3. [Engage with colleagues and improve practice](#apst6-3)
4. [Apply professional learning and improve student learning](#apst6-4)

### [7. Engage professionally with colleagues, parents/carers and the community](#apst7)
1. [Meet professional ethics and responsibilities](#apst7-1)
2. [Comply with legislative, administrative and organisational requirements](#apst7-2)
3. [Engage with the parents/carers](#apst7-3)
4. [Engage with professional teaching networks and broader communities](#apst7-4)


<!-- <div class="indicator-selector">
	<button id="btn-graduate" onclick="selectTab('content-graduate')">Graduate</button>
	<button id="btn-proficient" onclick="selectTab('content-proficient')">Proficient</button>
	<button id="btn-accomplished" onclick="selectTab('content-accomplished')">Highly Accomplished</button>
	<button id="btn-lead" onclick="selectTab('content-lead')">Lead</button>
</div>-->

{% for heading in site.data.standard-heading %}
# {{ heading.standard }} {#{{ heading.id }}}
<table>
    <col style="width:25%">
	<col style="width:75%">
    <tr>
		<th>Standard</th>
		<th>Reflection and Evidence against Standard</th>
	</tr>
{%- for standard in site.data.standard-indicators %}
    {%- if standard.id contains heading.id %}
    <tr>
		<td id="{{ standard.id }}">
			<p>
				<strong>{{ standard.descriptor }}</strong>
			</p>
			<div id="content-graduate" class="indicator">
				<p>
					<strong>Graduate Level:</strong> {{standard.indicator-graduate}}
				</p>
			</div>
			<div id="content-proficient" class="indicator" style="display:none">
				<p>
					<strong>Proficient Level:</strong> {{standard.indicator-proficient}}
				</p>
			</div>
			<div id="content-accomplished" class="indicator" style="display:none">
				<p>
					<strong>Highly Accomplished Level:</strong> {{standard.indicator-accomplished}}
				</p>
			</div>
			<div id="content-lead" class="indicator" style="display:none">
				<p>
					<strong>Lead Level:</strong> {{standard.indicator-lead}}
				</p>
			</div>
		</td>
		<td>
			{% for evidence in site.data.standard-descriptors %}
				{%- if evidence.id contains standard.id %}
            <p>
                {{ evidence.reflection }}
            </p>
			<p>
				{{ evidence.evidence }}
			</p>
				{% endif %}
			{% endfor %}
            <p>
			    <a href="{{ site.url }}/{{ site.baseurl }}/apst/{{ standard.id | slice: 4, 6 }}"> For evidence and further reflections see here</a>.
            </p>
        </td>
	</tr>
    {% endif %}
{% endfor %}
</table>
{% endfor %}
<script>
	function selectTab(currentIndicator) {
  		var i;
  		var x = document.getElementsByClassName("indicator");
  		for (i = 0; i < x.length; i++) {
    		x[i].style.display = "none";
  		}
  		document.getElementById(currentIndicator).style.display = "block";
	}
</script>