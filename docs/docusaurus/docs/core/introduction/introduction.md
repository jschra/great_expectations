---
title: Introduction to GX Core
description: Learn about GX Core components and workflows and try out the GX Core Python library.
hide_feedback_survey: true
hide_title: true
---
import GxData from '../_core_components/_data.jsx'

import LinkCardGrid from '@site/src/components/LinkCardGrid';
import LinkCard from '@site/src/components/LinkCard';
import OverviewCard from '@site/src/components/OverviewCard';

<OverviewCard title={frontMatter.title}>
  Learn about key Great Expectations (GX) Core components and workflows. Use the GX Core Python library and provided sample data to create a data validation workflow.
</OverviewCard>

<LinkCardGrid>

  <LinkCard 
    topIcon 
    label="GX Core overview"
    description="Learn about GX Core components and workflows."
    to="/core/introduction/gx_overview" 
    icon="/img/overview_icon.svg" 
  />

  <LinkCard 
    topIcon 
    label="Try GX Core"
    description="Walk through example GX Core workflows using sample data."
    to="/core/introduction/try_gx" 
    icon="/img/workflow_icon.svg" 
  />

</LinkCardGrid>